# WcPostQueryOpen

- ea: `0x1400149c0`
- end: `0x140014acc`
- name: `WcPostQueryOpen`
- size: `268`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001580`
- `0x140001b00`
- `0x140004198`
- `0x1400149c0`
- `0x1400260d0`

## string_xrefs

- `0x140014a95`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcPostQueryOpen(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  bool v2; // sf
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  _DWORD *EaList; // rbp
  unsigned int v8; // ebx
  int v9; // edx
  int v10; // eax
  int v11; // eax
  unsigned int v12; // eax
  int v13; // [rsp+70h] [rbp+8h] BYREF

  v2 = CallbackData->IoStatus.Status < 0;
  v13 = 0;
  if ( v2 )
    return 2;
  Iopb = CallbackData->Iopb;
  if ( Iopb->Parameters.Create.EaLength == 71 )
  {
    WcHandleQueryOnCreateEcp(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
    return 0;
  }
  EaList = Iopb->Parameters.QueryEa.EaList;
  v8 = 0;
  if ( (EaList[14] & 0x400) != 0 )
  {
    if ( !(unsigned __int8)WcUnionsExistForInstance(*(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), &v13, 0) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 3;
        WPP_RECORDER_SF_sD(
          wil_details_featureDescriptors_a->DeviceExtension,
          v9,
          5,
          83,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          152);
      }
      return v8;
    }
    v10 = EaList[15];
    if ( v10 == v13 )
    {
      if ( WcIsSiloFileObject(*(struct _FLT_INSTANCE **)(a2 + 24), *(_QWORD *)(a2 + 32)) )
      {
        v11 = EaList[14];
        EaList[15] = 0;
        v12 = v11 & 0xFFFFE9FF;
        if ( !v12 )
          v12 = 128;
        EaList[14] = v12;
        WcHandleQueryOnCreateEcp(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
        return v8;
      }
      return 2;
    }
    if ( v10 == -1610612705 )
      return 2;
  }
  return v8;
}

```

## disassembly

```asm
0x1400149c0  push    rbx
0x1400149c2  push    rbp
0x1400149c3  push    rsi
0x1400149c4  push    rdi
0x1400149c5  sub     rsp, 48h
0x1400149c9  cmp     dword ptr [rcx+18h], 0
0x1400149cd  mov     rdi, rdx
0x1400149d0  mov     rsi, rcx
0x1400149d3  mov     [rsp+68h+arg_0], 0
0x1400149db  jl      loc_140014A6D
0x1400149e1  mov     rax, [rcx+10h]
0x1400149e5  cmp     dword ptr [rax+30h], 47h ; 'G'
0x1400149e9  jnz     short loc_1400149FC
0x1400149eb  mov     r8, [rdx+20h]; FileObject
0x1400149ef  mov     rdx, [rdx+18h]; Instance
0x1400149f3  call    WcHandleQueryOnCreateEcp
0x1400149f8  xor     eax, eax
0x1400149fa  jmp     short loc_140014A74
0x1400149fc  mov     rbp, [rax+20h]
0x140014a00  xor     ebx, ebx
0x140014a02  test    dword ptr [rbp+38h], 400h
0x140014a09  jz      short loc_140014A72
0x140014a0b  mov     rdx, [rdx+20h]
0x140014a0f  lea     r8, [rsp+68h+arg_0]
0x140014a14  mov     rcx, [rdi+18h]
0x140014a18  xor     r9d, r9d
0x140014a1b  call    WcUnionsExistForInstance
0x140014a20  test    al, al
0x140014a22  jz      short loc_140014A7E
0x140014a24  mov     eax, [rbp+3Ch]
0x140014a27  cmp     eax, [rsp+68h+arg_0]
0x140014a2b  jnz     short loc_140014A66
0x140014a2d  mov     rdx, [rdi+20h]
0x140014a31  mov     rcx, [rdi+18h]
0x140014a35  call    WcIsSiloFileObject
0x140014a3a  test    al, al
0x140014a3c  jz      short loc_140014A6D
0x140014a3e  mov     eax, [rbp+38h]
0x140014a41  mov     ecx, 80h
0x140014a46  mov     [rbp+3Ch], ebx
0x140014a49  and     eax, 0FFFFE9FFh
0x140014a4e  cmovz   eax, ecx
0x140014a51  mov     rcx, rsi; CallbackData
0x140014a54  mov     [rbp+38h], eax
0x140014a57  mov     r8, [rdi+20h]; FileObject
0x140014a5b  mov     rdx, [rdi+18h]; Instance
0x140014a5f  call    WcHandleQueryOnCreateEcp
0x140014a64  jmp     short loc_140014A72
0x140014a66  cmp     eax, 0A000001Fh
0x140014a6b  jnz     short loc_140014A72
0x140014a6d  mov     ebx, 2
0x140014a72  mov     eax, ebx
0x140014a74  add     rsp, 48h
0x140014a78  pop     rdi
0x140014a79  pop     rsi
0x140014a7a  pop     rbp
0x140014a7b  pop     rbx
0x140014a7c  retn
0x140014a7e  lea     rax, WPP_RECORDER_INITIALIZED
0x140014a85  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014a8c  jz      short loc_140014A72
0x140014a8e  mov     rcx, cs:wil_details_featureDescriptors_a
0x140014a95  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140014a9c  mov     r9d, 53h ; 'S'
0x140014aa2  mov     [rsp+68h+var_38], 0E98h
0x140014aaa  mov     [rsp+68h+var_40], rax
0x140014aaf  mov     dl, 3
0x140014ab1  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140014ab8  mov     rcx, [rcx+40h]
0x140014abc  lea     r8d, [r9-4Eh]
0x140014ac0  mov     [rsp+68h+var_48], rax
0x140014ac5  call    WPP_RECORDER_SF_sD
0x140014aca  jmp     short loc_140014A72
```
