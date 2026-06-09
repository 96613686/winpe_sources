# pGetNewMachineOU(_IMG_SERVER_CONTEXT *,void *,ushort * *)

- ea: `0x18000baf8`
- end: `0x18000bdbd`
- name: `?pGetNewMachineOU@@YAJPEAU_IMG_SERVER_CONTEXT@@PEAXPEAPEAG@Z`
- size: `709`
- prototype: `__int64 __fastcall(struct _IMG_SERVER_CONTEXT *, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180002e64`

## callees

- `0x18000baf8`
- `0x18000cbd4`
- `0x180017010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bd7c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bd7c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bca9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bca9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd36`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd4e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd63`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd36`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd4e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd63`
- `WDSSRV!WdsImpersonateClient` at `0x18000bc33`
- `WDSSRV!WdsImpersonateClient` at `0x18000bc33`
- `WDSSRV!WdsRevertToSelf` at `0x18000bc74`
- `WDSSRV!WdsRevertToSelf` at `0x18000bc94`
- `WDSSRV!WdsRevertToSelf` at `0x18000bc74`
- `WDSSRV!WdsRevertToSelf` at `0x18000bc94`
- `WdsCommonLib!?GetCurrentUser@@YAKPEAPEAGPEBG@Z` at `0x18000bc5f`
- `WdsCommonLib!?GetCurrentUser@@YAKPEAPEAGPEBG@Z` at `0x18000bc5f`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000bd08`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000bd21`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000bd08`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000bd21`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x18000bcc2`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x18000bcc2`

## pseudocode

```c
__int64 __fastcall pGetNewMachineOU(struct _IMG_SERVER_CONTEXT *a1, void *a2, unsigned __int16 **a3)
{
  OLECHAR *v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  signed int CurrentUser; // eax
  bool v18; // cc
  __int64 v19; // rdx
  __int64 v20; // r8
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  BSTR v23; // [rsp+38h] [rbp-18h] BYREF
  __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-8h] BYREF
  __int16 v26; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+98h] [rbp+48h] BYREF

  v27 = 3;
  bstrString = 0;
  v23 = 0;
  psz = 0;
  v26 = 0;
  v6 = 0;
  v24 = 0;
  if ( a3 )
  {
    v7 = (*(unsigned int (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)a1 + 8) + 152LL))(
           *((_QWORD *)a1 + 8),
           &bstrString);
    if ( (int)ElValidateHr_1(v7, v8, v9, 1314) >= 0 )
    {
      v7 = (*(unsigned int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)a1 + 5) + 88LL))(*((_QWORD *)a1 + 5), &v24);
      if ( (int)ElValidateHr_1(v7, v10, v11, 1321) >= 0 )
      {
        v7 = (*(unsigned int (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v24 + 176LL))(v24, &v26);
        if ( (int)ElValidateHr_1(v7, v12, v13, 1324) >= 0 )
        {
          if ( v24 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            v24 = 0;
          }
          if ( v26 )
          {
            v7 = (*(unsigned int (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 8) + 200LL))(
                   *((_QWORD *)a1 + 8),
                   &v27);
            if ( (int)ElValidateHr_1(v7, v14, v15, 1350) >= 0 )
            {
              v16 = WdsImpersonateClient(a2);
              LODWORD(v7) = v16;
              if ( v16 )
              {
                if ( v16 > 0 )
                  LODWORD(v7) = (unsigned __int16)v16 | 0x80070000;
              }
              else
              {
                CurrentUser = GetCurrentUser(&psz, 0);
                LODWORD(v7) = CurrentUser;
                v18 = CurrentUser <= 0;
                if ( CurrentUser
                  || (CurrentUser = WdsRevertToSelf(a2), LODWORD(v7) = CurrentUser, v18 = CurrentUser <= 0, CurrentUser) )
                {
                  if ( !v18 )
                    LODWORD(v7) = (unsigned __int16)CurrentUser | 0x80070000;
                  WdsRevertToSelf(a2);
                }
                else
                {
                  v6 = SysAllocString(psz);
                  CMRSWLock::ReaderLock((CMRSWLock *)g_Lock);
                  v7 = (*(unsigned int (__fastcall **)(_QWORD, OLECHAR *, _QWORD, BSTR, BSTR *))(**((_QWORD **)a1 + 10)
                                                                                               + 120LL))(
                         *((_QWORD *)a1 + 10),
                         v6,
                         v27,
                         bstrString,
                         &v23);
                  if ( (int)ElValidateHr_1(v7, v19, v20, 1405) < 0 )
                  {
                    CMRSWLock::ReaderRelease((CMRSWLock *)g_Lock);
                  }
                  else
                  {
                    CMRSWLock::ReaderRelease((CMRSWLock *)g_Lock);
                    *a3 = v23;
                    v23 = 0;
                  }
                }
              }
            }
          }
          else
          {
            *a3 = bstrString;
            bstrString = 0;
          }
        }
      }
    }
  }
  else
  {
    LODWORD(v7) = -2147024809;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v6 )
    SysFreeString(v6);
  if ( v23 )
  {
    SysFreeString(v23);
    v23 = 0;
  }
  if ( psz )
  {
    operator delete[](psz);
    psz = 0;
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000baf8  mov     [rsp-28h+arg_0], rbx
0x18000bafd  mov     [rsp-28h+arg_8], rsi
0x18000bb02  push    rbp
0x18000bb03  push    rdi
0x18000bb04  push    r12
0x18000bb06  push    r14
0x18000bb08  push    r15
0x18000bb0a  mov     rbp, rsp
0x18000bb0d  sub     rsp, 50h
0x18000bb11  xor     r12d, r12d
0x18000bb14  mov     [rbp+arg_18], 3
0x18000bb1b  mov     [rbp+bstrString], r12
0x18000bb1f  mov     r14, r8
0x18000bb22  mov     [rbp+var_18], r12
0x18000bb26  mov     rsi, rdx
0x18000bb29  mov     [rbp+psz], r12
0x18000bb2d  mov     r15, rcx
0x18000bb30  mov     [rbp+arg_10], r12w
0x18000bb35  mov     edi, r12d
0x18000bb38  mov     [rbp+var_10], r12
0x18000bb3c  test    r8, r8
0x18000bb3f  jnz     short loc_18000BB4B
0x18000bb41  mov     ebx, 80070057h
0x18000bb46  jmp     loc_18000BD2D
0x18000bb4b  mov     rcx, [rcx+40h]
0x18000bb4f  lea     rdx, [rbp+bstrString]
0x18000bb53  mov     rax, [rcx]
0x18000bb56  mov     rax, [rax+98h]
0x18000bb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb62  mov     r9d, 522h
0x18000bb68  mov     ecx, eax
0x18000bb6a  mov     ebx, eax
0x18000bb6c  call    ElValidateHr_1
0x18000bb71  test    eax, eax
0x18000bb73  js      loc_18000BD2D
0x18000bb79  mov     rcx, [r15+28h]
0x18000bb7d  lea     rdx, [rbp+var_10]
0x18000bb81  mov     rax, [rcx]
0x18000bb84  mov     rax, [rax+58h]
0x18000bb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb8d  mov     r9d, 529h
0x18000bb93  mov     ecx, eax
0x18000bb95  mov     ebx, eax
0x18000bb97  call    ElValidateHr_1
0x18000bb9c  test    eax, eax
0x18000bb9e  js      loc_18000BD2D
0x18000bba4  mov     rcx, [rbp+var_10]
0x18000bba8  lea     rdx, [rbp+arg_10]
0x18000bbac  mov     rax, [rcx]
0x18000bbaf  mov     rax, [rax+0B0h]
0x18000bbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbbb  mov     r9d, 52Ch
0x18000bbc1  mov     ecx, eax
0x18000bbc3  mov     ebx, eax
0x18000bbc5  call    ElValidateHr_1
0x18000bbca  test    eax, eax
0x18000bbcc  js      loc_18000BD2D
0x18000bbd2  mov     rcx, [rbp+var_10]
0x18000bbd6  test    rcx, rcx
0x18000bbd9  jz      short loc_18000BBEB
0x18000bbdb  mov     rax, [rcx]
0x18000bbde  mov     rax, [rax+10h]
0x18000bbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbe7  mov     [rbp+var_10], r12
0x18000bbeb  cmp     [rbp+arg_10], r12w
0x18000bbf0  jnz     short loc_18000BC02
0x18000bbf2  mov     rax, [rbp+bstrString]
0x18000bbf6  mov     [r14], rax
0x18000bbf9  mov     [rbp+bstrString], r12
0x18000bbfd  jmp     loc_18000BD2D
0x18000bc02  mov     rcx, [r15+40h]
0x18000bc06  lea     rdx, [rbp+arg_18]
0x18000bc0a  mov     rax, [rcx]
0x18000bc0d  mov     rax, [rax+0C8h]
0x18000bc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc19  mov     r9d, 546h
0x18000bc1f  mov     ecx, eax
0x18000bc21  mov     ebx, eax
0x18000bc23  call    ElValidateHr_1
0x18000bc28  test    eax, eax
0x18000bc2a  js      loc_18000BD2D
0x18000bc30  mov     rcx, rsi
0x18000bc33  call    cs:__imp_WdsImpersonateClient
0x18000bc3a  nop     dword ptr [rax+rax+00h]
0x18000bc3f  mov     ebx, eax
0x18000bc41  test    eax, eax
0x18000bc43  jz      short loc_18000BC59
0x18000bc45  jle     loc_18000BD2D
0x18000bc4b  movzx   ebx, ax
0x18000bc4e  or      ebx, 80070000h
0x18000bc54  jmp     loc_18000BD2D
0x18000bc59  xor     edx, edx
0x18000bc5b  lea     rcx, [rbp+psz]
0x18000bc5f  call    cs:__imp_?GetCurrentUser@@YAKPEAPEAGPEBG@Z; GetCurrentUser(ushort * *,ushort const *)
0x18000bc66  nop     dword ptr [rax+rax+00h]
0x18000bc6b  mov     ebx, eax
0x18000bc6d  test    eax, eax
0x18000bc6f  jnz     short loc_18000BC86
0x18000bc71  mov     rcx, rsi
0x18000bc74  call    cs:__imp_WdsRevertToSelf
0x18000bc7b  nop     dword ptr [rax+rax+00h]
0x18000bc80  mov     ebx, eax
0x18000bc82  test    eax, eax
0x18000bc84  jz      short loc_18000BCA5
0x18000bc86  jle     short loc_18000BC91
0x18000bc88  movzx   ebx, ax
0x18000bc8b  or      ebx, 80070000h
0x18000bc91  mov     rcx, rsi
0x18000bc94  call    cs:__imp_WdsRevertToSelf
0x18000bc9b  nop     dword ptr [rax+rax+00h]
0x18000bca0  jmp     loc_18000BD2D
0x18000bca5  mov     rcx, [rbp+psz]; psz
0x18000bca9  call    cs:__imp_SysAllocString
0x18000bcb0  nop     dword ptr [rax+rax+00h]
0x18000bcb5  lea     rsi, ?g_Lock@@3VCMRSWLock@@A; CMRSWLock g_Lock
0x18000bcbc  mov     rdi, rax
0x18000bcbf  mov     rcx, rsi
0x18000bcc2  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x18000bcc9  nop     dword ptr [rax+rax+00h]
0x18000bcce  mov     rcx, [r15+50h]
0x18000bcd2  mov     r9, [rbp+bstrString]
0x18000bcd6  mov     r8d, [rbp+arg_18]
0x18000bcda  mov     rdx, [rcx]
0x18000bcdd  mov     rax, [rdx+78h]
0x18000bce1  lea     rdx, [rbp+var_18]
0x18000bce5  mov     [rsp+50h+var_30], rdx
0x18000bcea  mov     rdx, rdi
0x18000bced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf2  mov     r9d, 57Dh
0x18000bcf8  mov     ecx, eax
0x18000bcfa  mov     ebx, eax
0x18000bcfc  call    ElValidateHr_1
0x18000bd01  mov     rcx, rsi
0x18000bd04  test    eax, eax
0x18000bd06  js      short loc_18000BD21
0x18000bd08  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000bd0f  nop     dword ptr [rax+rax+00h]
0x18000bd14  mov     rax, [rbp+var_18]
0x18000bd18  mov     [r14], rax
0x18000bd1b  mov     [rbp+var_18], r12
0x18000bd1f  jmp     short loc_18000BD2D
0x18000bd21  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000bd28  nop     dword ptr [rax+rax+00h]
0x18000bd2d  mov     rcx, [rbp+bstrString]; bstrString
0x18000bd31  test    rcx, rcx
0x18000bd34  jz      short loc_18000BD46
0x18000bd36  call    cs:__imp_SysFreeString
0x18000bd3d  nop     dword ptr [rax+rax+00h]
0x18000bd42  mov     [rbp+bstrString], r12
0x18000bd46  test    rdi, rdi
0x18000bd49  jz      short loc_18000BD5A
0x18000bd4b  mov     rcx, rdi; bstrString
0x18000bd4e  call    cs:__imp_SysFreeString
0x18000bd55  nop     dword ptr [rax+rax+00h]
0x18000bd5a  mov     rcx, [rbp+var_18]; bstrString
0x18000bd5e  test    rcx, rcx
0x18000bd61  jz      short loc_18000BD73
0x18000bd63  call    cs:__imp_SysFreeString
0x18000bd6a  nop     dword ptr [rax+rax+00h]
0x18000bd6f  mov     [rbp+var_18], r12
0x18000bd73  mov     rcx, [rbp+psz]
0x18000bd77  test    rcx, rcx
0x18000bd7a  jz      short loc_18000BD8C
0x18000bd7c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000bd83  nop     dword ptr [rax+rax+00h]
0x18000bd88  mov     [rbp+psz], r12
0x18000bd8c  mov     rcx, [rbp+var_10]
0x18000bd90  test    rcx, rcx
0x18000bd93  jz      short loc_18000BDA1
0x18000bd95  mov     rax, [rcx]
0x18000bd98  mov     rax, [rax+10h]
0x18000bd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda1  lea     r11, [rsp+50h+var_s0]
0x18000bda6  mov     eax, ebx
0x18000bda8  mov     rbx, [r11+30h]
0x18000bdac  mov     rsi, [r11+38h]
0x18000bdb0  mov     rsp, r11
0x18000bdb3  pop     r15
0x18000bdb5  pop     r14
0x18000bdb7  pop     r12
0x18000bdb9  pop     rdi
0x18000bdba  pop     rbp
0x18000bdbb  retn
```
