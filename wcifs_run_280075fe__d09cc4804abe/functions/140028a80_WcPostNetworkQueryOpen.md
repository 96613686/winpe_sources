# WcPostNetworkQueryOpen

- ea: `0x140028a80`
- end: `0x140028c9e`
- name: `WcPostNetworkQueryOpen`
- size: `542`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140001b00`
- `0x1400020c4`
- `0x140007c60`
- `0x1400080c0`
- `0x140026080`
- `0x140028a80`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140028b35`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140028b35`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028ae6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028ae6`
- `FLTMGR!FltQueryInformationByName` at `0x140028bd3`
- `FLTMGR!FltQueryInformationByName` at `0x140028bd3`
- `FLTMGR!FltObjectDereference` at `0x140028b1f`
- `FLTMGR!FltObjectDereference` at `0x140028b1f`

## string_xrefs

- `0x140028c2d`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcPostNetworkQueryOpen(PFLT_CALLBACK_DATA CallbackData, __int64 a2, void *a3)
{
  struct _FLT_FILE_NAME_INFORMATION *v6; // rcx
  void **v7; // rax
  void **v8; // rcx
  _DWORD *EaList; // r14
  __int64 v11; // rdx
  int v12; // eax
  int v13; // edx
  unsigned int v14; // eax
  _BYTE v15[48]; // [rsp+40h] [rbp-69h] BYREF
  __int128 v16; // [rsp+70h] [rbp-39h] BYREF
  _DWORD v17[20]; // [rsp+80h] [rbp-29h] BYREF

  memset(v15, 0, 44);
  v16 = 0;
  memset(v17, 0, 0x48u);
  if ( CallbackData->IoStatus.Status < 0 )
    goto LABEL_2;
  EaList = CallbackData->Iopb->Parameters.QueryEa.EaList;
  if ( (EaList[12] & 0x400) == 0 )
    goto LABEL_2;
  v11 = *(_QWORD *)(a2 + 24);
  *(_QWORD *)&v15[16] = *((_QWORD *)a3 + 6) + 8LL;
  *(_DWORD *)v15 = 48;
  *(_QWORD *)&v15[8] = 0;
  *(_DWORD *)&v15[24] = 512;
  *(_OWORD *)&v15[32] = 0;
  v12 = ((__int64 (__fastcall *)(PFLT_FILTER, __int64, _BYTE *, __int128 *, _DWORD *, int, int, _QWORD))FltQueryInformationByName)(
          Globals,
          v11,
          v15,
          &v16,
          v17,
          72,
          68,
          0);
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        5,
        82,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        223,
        v12);
    }
    goto LABEL_15;
  }
  if ( v17[15] != *((_DWORD *)a3 + 4) )
  {
    if ( v17[15] != -1610612705 )
      goto LABEL_2;
    goto LABEL_15;
  }
  if ( !(unsigned __int8)WcIsSiloFileObject(*(_QWORD *)(a2 + 24)) )
  {
LABEL_15:
    CallbackData->IoStatus.Status = -1071906812;
    CallbackData->IoStatus.Information = 0;
    goto LABEL_2;
  }
  v14 = EaList[12] & 0xFFFFE9FF;
  if ( !v14 )
    v14 = 128;
  EaList[12] = v14;
  WcHandleQueryOnCreateEcp(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
LABEL_2:
  if ( a3 )
  {
    v6 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)a3 + 6);
    if ( v6 )
      FltReleaseFileNameInformation(v6);
    v7 = *(void ***)a3;
    if ( *(void **)a3 != a3 )
    {
      if ( v7[1] != a3 || (v8 = (void **)*((_QWORD *)a3 + 1), *v8 != a3) )
        __fastfail(3u);
      *v8 = v7;
      v7[1] = v8;
      FltObjectDereference(Globals);
    }
    ExFreeToPagedLookasideList(&stru_14000E400, a3);
  }
  return 0;
}

```

## disassembly

```asm
0x140028a80  push    rbp
0x140028a82  push    rbx
0x140028a83  push    rsi
0x140028a84  push    rdi
0x140028a85  push    r14
0x140028a87  lea     rbp, [rsp-37h]
0x140028a8c  sub     rsp, 0E0h
0x140028a93  mov     rax, cs:__security_cookie
0x140028a9a  xor     rax, rsp
0x140028a9d  mov     [rbp+57h+var_30], rax
0x140028aa1  xorps   xmm0, xmm0
0x140028aa4  xor     eax, eax
0x140028aa6  mov     rbx, r8
0x140028aa9  mov     rsi, rdx
0x140028aac  mov     rdi, rcx
0x140028aaf  xor     edx, edx; Val
0x140028ab1  movups  [rbp+57h+var_B0], xmm0
0x140028ab5  lea     r8d, [rax+48h]; Size
0x140028ab9  lea     rcx, [rbp+57h+var_80]; void *
0x140028abd  movups  [rbp+57h+var_C0], xmm0
0x140028ac1  movups  [rbp+57h+var_B0+0Ch], xmm0
0x140028ac5  movups  [rbp+57h+var_90], xmm0
0x140028ac9  call    memset
0x140028ace  cmp     dword ptr [rdi+18h], 0
0x140028ad2  jge     loc_140028B5E
0x140028ad8  test    rbx, rbx
0x140028adb  jz      short loc_140028B41
0x140028add  mov     rcx, [rbx+30h]; FileNameInformation
0x140028ae1  test    rcx, rcx
0x140028ae4  jz      short loc_140028AF2
0x140028ae6  call    cs:__imp_FltReleaseFileNameInformation
0x140028aed  nop     dword ptr [rax+rax+00h]
0x140028af2  mov     rax, [rbx]
0x140028af5  cmp     rax, rbx
0x140028af8  jz      short loc_140028B2B
0x140028afa  cmp     [rax+8], rbx
0x140028afe  jnz     loc_140028C97
0x140028b04  mov     rcx, [rbx+8]
0x140028b08  cmp     [rcx], rbx
0x140028b0b  jnz     loc_140028C97
0x140028b11  mov     [rcx], rax
0x140028b14  mov     [rax+8], rcx
0x140028b18  mov     rcx, cs:Globals; FltObject
0x140028b1f  call    cs:__imp_FltObjectDereference
0x140028b26  nop     dword ptr [rax+rax+00h]
0x140028b2b  mov     rdx, rbx; Entry
0x140028b2e  lea     rcx, stru_14000E400; Lookaside
0x140028b35  call    cs:__imp_ExFreeToPagedLookasideList
0x140028b3c  nop     dword ptr [rax+rax+00h]
0x140028b41  xor     eax, eax
0x140028b43  mov     rcx, [rbp+57h+var_30]
0x140028b47  xor     rcx, rsp; StackCookie
0x140028b4a  call    __security_check_cookie
0x140028b4f  add     rsp, 0E0h
0x140028b56  pop     r14
0x140028b58  pop     rdi
0x140028b59  pop     rsi
0x140028b5a  pop     rbx
0x140028b5b  pop     rbp
0x140028b5c  retn
0x140028b5e  mov     rax, [rdi+10h]
0x140028b62  mov     r14, [rax+20h]
0x140028b66  test    dword ptr [r14+30h], 400h
0x140028b6e  jz      loc_140028AD8
0x140028b74  mov     rax, [rbx+30h]
0x140028b78  lea     r9, [rbp+57h+var_90]
0x140028b7c  mov     rdx, [rsi+18h]
0x140028b80  lea     r8, [rbp+57h+var_C0]
0x140028b84  mov     rcx, cs:Globals
0x140028b8b  add     rax, 8
0x140028b8f  mov     [rsp+100h+var_C8], 0
0x140028b98  xorps   xmm0, xmm0
0x140028b9b  mov     qword ptr [rbp+57h+var_B0], rax
0x140028b9f  lea     rax, [rbp+57h+var_80]
0x140028ba3  mov     [rsp+100h+var_D0], 44h ; 'D'
0x140028bab  mov     dword ptr [rsp+100h+var_D8], 48h ; 'H'
0x140028bb3  mov     [rsp+100h+var_E0], rax
0x140028bb8  mov     dword ptr [rbp+57h+var_C0], 30h ; '0'
0x140028bbf  mov     qword ptr [rbp+57h+var_C0+8], 0
0x140028bc7  mov     dword ptr [rbp+57h+var_B0+8], 200h
0x140028bce  movdqu  [rbp+57h+var_A0], xmm0
0x140028bd3  call    cs:__imp_FltQueryInformationByName
0x140028bda  nop     dword ptr [rax+rax+00h]
0x140028bdf  test    eax, eax
0x140028be1  js      short loc_140028C0A
0x140028be3  mov     eax, [rbp+57h+var_44]
0x140028be6  cmp     eax, [rbx+10h]
0x140028be9  jz      short loc_140028C5C
0x140028beb  cmp     eax, 0A000001Fh
0x140028bf0  jnz     loc_140028AD8
0x140028bf6  mov     dword ptr [rdi+18h], 0C01C0004h
0x140028bfd  mov     qword ptr [rdi+20h], 0
0x140028c05  jmp     loc_140028AD8
0x140028c0a  lea     rcx, WPP_RECORDER_INITIALIZED
0x140028c11  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140028c18  jz      short loc_140028BF6
0x140028c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c21  mov     r9d, 52h ; 'R'
0x140028c27  mov     dword ptr [rsp+100h+var_C8], eax
0x140028c2b  mov     dl, 2
0x140028c2d  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140028c34  mov     [rsp+100h+var_D0], 0DDFh
0x140028c3c  mov     [rsp+100h+var_D8], rax
0x140028c41  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140028c48  mov     rcx, [rcx+40h]
0x140028c4c  lea     r8d, [r9-4Dh]
0x140028c50  mov     [rsp+100h+var_E0], rax
0x140028c55  call    WPP_RECORDER_SF_sDd
0x140028c5a  jmp     short loc_140028BF6
0x140028c5c  mov     rdx, [rsi+20h]
0x140028c60  mov     rcx, [rsi+18h]
0x140028c64  call    WcIsSiloFileObject
0x140028c69  test    al, al
0x140028c6b  jz      short loc_140028BF6
0x140028c6d  mov     eax, [r14+30h]
0x140028c71  mov     ecx, 80h
0x140028c76  and     eax, 0FFFFE9FFh
0x140028c7b  cmovz   eax, ecx
0x140028c7e  mov     rcx, rdi; CallbackData
0x140028c81  mov     [r14+30h], eax
0x140028c85  mov     r8, [rsi+20h]; FileObject
0x140028c89  mov     rdx, [rsi+18h]; Instance
0x140028c8d  call    WcHandleQueryOnCreateEcp
0x140028c92  jmp     loc_140028AD8
0x140028c97  mov     ecx, 3
0x140028c9c  int     29h; Win8: RtlFailFast(ecx)
```
