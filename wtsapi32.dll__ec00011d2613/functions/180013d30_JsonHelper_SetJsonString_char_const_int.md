# JsonHelper::SetJsonString(char const *,int)

- ea: `0x180013d30`
- end: `0x180013e20`
- name: `?SetJsonString@JsonHelper@@UEAAJPEBDH@Z`
- size: `240`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const char *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x180006734`
- `0x180013d30`
- `0x1800144a4`
- `0x180014bb0`
- `0x180015488`
- `0x180016010`

## string_xrefs

- `0x180013dd7`: `this->SetJsonString failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::SetJsonString(JsonHelper *this, const char *a2, int a3)
{
  int v4; // ebx
  int ActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  __int64 v8; // rcx
  int *v10; // [rsp+20h] [rbp-18h]
  void *Block; // [rsp+58h] [rbp+20h] BYREF

  Block = 0;
  v4 = JsonHelper::UTF8ToWideChar(this, a2, a3, (unsigned __int16 **)&Block, v10);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(JsonHelper *, void *))(*(_QWORD *)this + 64LL))(this, Block);
    if ( v4 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v8, &WPP_GLOBAL_Control);
      v6 = 33;
      v7 = "this->SetJsonString failed!";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
    v6 = 32;
    v7 = "UTF8ToWideChar failed!";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v7,
      v4);
  }
  if ( Block )
    operator delete(Block);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013d30  mov     [rsp+arg_0], rbx
0x180013d35  push    rsi
0x180013d36  sub     rsp, 30h
0x180013d3a  lea     r9, [rsp+38h+Block]; unsigned __int16 **
0x180013d3f  mov     [rsp+38h+Block], 0
0x180013d48  mov     rsi, rcx
0x180013d4b  call    ?UTF8ToWideChar@JsonHelper@@AEAAJPEBDHPEAPEAGPEAH@Z; JsonHelper::UTF8ToWideChar(char const *,int,ushort * *,int *)
0x180013d50  mov     ebx, eax
0x180013d52  test    eax, eax
0x180013d54  jns     short loc_180013D94
0x180013d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d5d  lea     rdx, WPP_GLOBAL_Control
0x180013d64  cmp     rcx, rdx
0x180013d67  jz      loc_180013E01
0x180013d6d  test    byte ptr [rcx+1Ch], 8
0x180013d71  jz      loc_180013E01
0x180013d77  cmp     byte ptr [rcx+19h], 2
0x180013d7b  jb      loc_180013E01
0x180013d81  call    RdpX_GetActivityIdPrefix
0x180013d86  mov     edx, 20h ; ' '
0x180013d8b  lea     rcx, aUtf8towidechar_0; "UTF8ToWideChar failed!"
0x180013d92  jmp     short loc_180013DDE
0x180013d94  mov     rax, [rsi]
0x180013d97  mov     rcx, rsi
0x180013d9a  mov     rdx, [rsp+38h+Block]
0x180013d9f  mov     rax, [rax+40h]
0x180013da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da8  mov     ebx, eax
0x180013daa  test    eax, eax
0x180013dac  jns     short loc_180013E01
0x180013dae  mov     rax, cs:WPP_GLOBAL_Control
0x180013db5  lea     rdx, WPP_GLOBAL_Control
0x180013dbc  cmp     rax, rdx
0x180013dbf  jz      short loc_180013E01
0x180013dc1  test    byte ptr [rax+1Ch], 8
0x180013dc5  jz      short loc_180013E01
0x180013dc7  cmp     byte ptr [rax+19h], 2
0x180013dcb  jb      short loc_180013E01
0x180013dcd  call    RdpX_GetActivityIdPrefix
0x180013dd2  mov     edx, 21h ; '!'
0x180013dd7  lea     rcx, aThisSetjsonstr; "this->SetJsonString failed!"
0x180013dde  mov     [rsp+38h+var_10], ebx
0x180013de2  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180013de9  mov     [rsp+38h+var_18], rcx
0x180013dee  mov     r9d, eax
0x180013df1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013df8  mov     rcx, [rcx+10h]
0x180013dfc  call    WPP_SF_DsD
0x180013e01  cmp     [rsp+38h+Block], 0
0x180013e07  jz      short loc_180013E13
0x180013e09  mov     rcx, [rsp+38h+Block]; Block
0x180013e0e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013e13  mov     eax, ebx
0x180013e15  mov     rbx, [rsp+38h+arg_0]
0x180013e1a  add     rsp, 30h
0x180013e1e  pop     rsi
0x180013e1f  retn
```
