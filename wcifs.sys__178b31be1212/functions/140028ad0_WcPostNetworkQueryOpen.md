# WcPostNetworkQueryOpen

- ea: `0x140028ad0`
- end: `0x140028cee`
- name: `WcPostNetworkQueryOpen`
- size: `542`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140001b00`
- `0x1400020c4`
- `0x140007c60`
- `0x1400080c0`
- `0x1400260d0`
- `0x140028ad0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140028b85`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140028b85`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028b36`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028b36`
- `FLTMGR!FltQueryInformationByName` at `0x140028c23`
- `FLTMGR!FltQueryInformationByName` at `0x140028c23`
- `FLTMGR!FltObjectDereference` at `0x140028b6f`
- `FLTMGR!FltObjectDereference` at `0x140028b6f`

## string_xrefs

- `0x140028c7d`: `onecore\base\fs\wci\wcifs\create.c`

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
  __int64 v15; // [rsp+38h] [rbp-71h]
  _BYTE v16[48]; // [rsp+40h] [rbp-69h] BYREF
  __int128 v17; // [rsp+70h] [rbp-39h] BYREF
  _DWORD v18[20]; // [rsp+80h] [rbp-29h] BYREF

  memset(v16, 0, 44);
  v17 = 0;
  memset(v18, 0, 0x48u);
  if ( CallbackData->IoStatus.Status < 0 )
    goto LABEL_2;
  EaList = CallbackData->Iopb->Parameters.QueryEa.EaList;
  if ( (EaList[12] & 0x400) == 0 )
    goto LABEL_2;
  v11 = *(_QWORD *)(a2 + 24);
  *(_QWORD *)&v16[16] = *((_QWORD *)a3 + 6) + 8LL;
  *(_DWORD *)v16 = 48;
  *(_QWORD *)&v16[8] = 0;
  *(_DWORD *)&v16[24] = 512;
  *(_OWORD *)&v16[32] = 0;
  v12 = ((__int64 (__fastcall *)(PFLT_FILTER, __int64, _BYTE *, __int128 *, _DWORD *, int, int, _QWORD))FltQueryInformationByName)(
          Globals,
          v11,
          v16,
          &v17,
          v18,
          72,
          68,
          0);
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v15) = v12;
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v13,
        5,
        82,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        223,
        v15);
    }
    goto LABEL_15;
  }
  if ( v18[15] != *((_DWORD *)a3 + 4) )
  {
    if ( v18[15] != -1610612705 )
      goto LABEL_2;
    goto LABEL_15;
  }
  if ( !WcIsSiloFileObject(*(struct _FLT_INSTANCE **)(a2 + 24), *(_QWORD *)(a2 + 32)) )
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
0x140028ad0  push    rbp
0x140028ad2  push    rbx
0x140028ad3  push    rsi
0x140028ad4  push    rdi
0x140028ad5  push    r14
0x140028ad7  lea     rbp, [rsp-37h]
0x140028adc  sub     rsp, 0E0h
0x140028ae3  mov     rax, cs:__security_cookie
0x140028aea  xor     rax, rsp
0x140028aed  mov     [rbp+57h+var_30], rax
0x140028af1  xorps   xmm0, xmm0
0x140028af4  xor     eax, eax
0x140028af6  mov     rbx, r8
0x140028af9  mov     rsi, rdx
0x140028afc  mov     rdi, rcx
0x140028aff  xor     edx, edx; Val
0x140028b01  movups  [rbp+57h+var_B0], xmm0
0x140028b05  lea     r8d, [rax+48h]; Size
0x140028b09  lea     rcx, [rbp+57h+var_80]; void *
0x140028b0d  movups  [rbp+57h+var_C0], xmm0
0x140028b11  movups  [rbp+57h+var_B0+0Ch], xmm0
0x140028b15  movups  [rbp+57h+var_90], xmm0
0x140028b19  call    memset
0x140028b1e  cmp     dword ptr [rdi+18h], 0
0x140028b22  jge     loc_140028BAE
0x140028b28  test    rbx, rbx
0x140028b2b  jz      short loc_140028B91
0x140028b2d  mov     rcx, [rbx+30h]; FileNameInformation
0x140028b31  test    rcx, rcx
0x140028b34  jz      short loc_140028B42
0x140028b36  call    cs:__imp_FltReleaseFileNameInformation
0x140028b3d  nop     dword ptr [rax+rax+00h]
0x140028b42  mov     rax, [rbx]
0x140028b45  cmp     rax, rbx
0x140028b48  jz      short loc_140028B7B
0x140028b4a  cmp     [rax+8], rbx
0x140028b4e  jnz     loc_140028CE7
0x140028b54  mov     rcx, [rbx+8]
0x140028b58  cmp     [rcx], rbx
0x140028b5b  jnz     loc_140028CE7
0x140028b61  mov     [rcx], rax
0x140028b64  mov     [rax+8], rcx
0x140028b68  mov     rcx, cs:Globals; FltObject
0x140028b6f  call    cs:__imp_FltObjectDereference
0x140028b76  nop     dword ptr [rax+rax+00h]
0x140028b7b  mov     rdx, rbx; Entry
0x140028b7e  lea     rcx, stru_14000E400; Lookaside
0x140028b85  call    cs:__imp_ExFreeToPagedLookasideList
0x140028b8c  nop     dword ptr [rax+rax+00h]
0x140028b91  xor     eax, eax
0x140028b93  mov     rcx, [rbp+57h+var_30]
0x140028b97  xor     rcx, rsp; StackCookie
0x140028b9a  call    __security_check_cookie
0x140028b9f  add     rsp, 0E0h
0x140028ba6  pop     r14
0x140028ba8  pop     rdi
0x140028ba9  pop     rsi
0x140028baa  pop     rbx
0x140028bab  pop     rbp
0x140028bac  retn
0x140028bae  mov     rax, [rdi+10h]
0x140028bb2  mov     r14, [rax+20h]
0x140028bb6  test    dword ptr [r14+30h], 400h
0x140028bbe  jz      loc_140028B28
0x140028bc4  mov     rax, [rbx+30h]
0x140028bc8  lea     r9, [rbp+57h+var_90]
0x140028bcc  mov     rdx, [rsi+18h]
0x140028bd0  lea     r8, [rbp+57h+var_C0]
0x140028bd4  mov     rcx, cs:Globals
0x140028bdb  add     rax, 8
0x140028bdf  mov     [rsp+100h+var_C8], 0
0x140028be8  xorps   xmm0, xmm0
0x140028beb  mov     qword ptr [rbp+57h+var_B0], rax
0x140028bef  lea     rax, [rbp+57h+var_80]
0x140028bf3  mov     [rsp+100h+var_D0], 44h ; 'D'
0x140028bfb  mov     dword ptr [rsp+100h+var_D8], 48h ; 'H'
0x140028c03  mov     [rsp+100h+var_E0], rax
0x140028c08  mov     dword ptr [rbp+57h+var_C0], 30h ; '0'
0x140028c0f  mov     qword ptr [rbp+57h+var_C0+8], 0
0x140028c17  mov     dword ptr [rbp+57h+var_B0+8], 200h
0x140028c1e  movdqu  [rbp+57h+var_A0], xmm0
0x140028c23  call    cs:__imp_FltQueryInformationByName
0x140028c2a  nop     dword ptr [rax+rax+00h]
0x140028c2f  test    eax, eax
0x140028c31  js      short loc_140028C5A
0x140028c33  mov     eax, [rbp+57h+var_44]
0x140028c36  cmp     eax, [rbx+10h]
0x140028c39  jz      short loc_140028CAC
0x140028c3b  cmp     eax, 0A000001Fh
0x140028c40  jnz     loc_140028B28
0x140028c46  mov     dword ptr [rdi+18h], 0C01C0004h
0x140028c4d  mov     qword ptr [rdi+20h], 0
0x140028c55  jmp     loc_140028B28
0x140028c5a  lea     rcx, WPP_RECORDER_INITIALIZED
0x140028c61  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140028c68  jz      short loc_140028C46
0x140028c6a  mov     rcx, cs:wil_details_featureDescriptors_a
0x140028c71  mov     r9d, 52h ; 'R'
0x140028c77  mov     dword ptr [rsp+100h+var_C8], eax
0x140028c7b  mov     dl, 2
0x140028c7d  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140028c84  mov     [rsp+100h+var_D0], 0DDFh
0x140028c8c  mov     [rsp+100h+var_D8], rax
0x140028c91  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140028c98  mov     rcx, [rcx+40h]
0x140028c9c  lea     r8d, [r9-4Dh]
0x140028ca0  mov     [rsp+100h+var_E0], rax
0x140028ca5  call    WPP_RECORDER_SF_sDd
0x140028caa  jmp     short loc_140028C46
0x140028cac  mov     rdx, [rsi+20h]
0x140028cb0  mov     rcx, [rsi+18h]
0x140028cb4  call    WcIsSiloFileObject
0x140028cb9  test    al, al
0x140028cbb  jz      short loc_140028C46
0x140028cbd  mov     eax, [r14+30h]
0x140028cc1  mov     ecx, 80h
0x140028cc6  and     eax, 0FFFFE9FFh
0x140028ccb  cmovz   eax, ecx
0x140028cce  mov     rcx, rdi; CallbackData
0x140028cd1  mov     [r14+30h], eax
0x140028cd5  mov     r8, [rsi+20h]; FileObject
0x140028cd9  mov     rdx, [rsi+18h]; Instance
0x140028cdd  call    WcHandleQueryOnCreateEcp
0x140028ce2  jmp     loc_140028B28
0x140028ce7  mov     ecx, 3
0x140028cec  int     29h; Win8: RtlFailFast(ecx)
```
