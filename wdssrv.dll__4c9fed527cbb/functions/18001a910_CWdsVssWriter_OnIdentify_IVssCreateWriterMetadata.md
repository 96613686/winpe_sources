# CWdsVssWriter::OnIdentify(IVssCreateWriterMetadata *)

- ea: `0x18001a910`
- end: `0x18001ac88`
- name: `?OnIdentify@CWdsVssWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z`
- size: `888`
- prototype: `bool __fastcall(CWdsVssWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a910`
- `0x18001ae58`
- `0x18001af54`
- `0x18001d010`

## import_xrefs

- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001ab57`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001ac02`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001ac3e`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001ac53`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001ab57`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001ac02`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001ac3e`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001ac53`
- `WdsServerCommonLib!ConcatenatePaths` at `0x18001ab8c`
- `WdsServerCommonLib!ConcatenatePaths` at `0x18001ab8c`
- `WdsServerCommonLib!?WcsDupHr@@YAJPEBGPEAPEAG@Z` at `0x18001aaab`
- `WdsServerCommonLib!?WcsDupHr@@YAJPEBGPEAPEAG@Z` at `0x18001aaab`
- `WdsServerCommonLib!?SysAllocStringHr@@YAJPEBGPEAPEAG@Z` at `0x18001aa07`
- `WdsServerCommonLib!?SysAllocStringHr@@YAJPEBGPEAPEAG@Z` at `0x18001aa07`
- `WdsServerCommonLib!?CreateComObject@@YAKPEBGAEBU_GUID@@PEAPEAX@Z` at `0x18001a9ce`
- `WdsServerCommonLib!?CreateComObject@@YAKPEBGAEBU_GUID@@PEAPEAX@Z` at `0x18001a9ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18001aad6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001aaef`
- `OLEAUT32!__imp_SysFreeString` at `0x18001aad6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001aaef`

## pseudocode

```c
bool __fastcall CWdsVssWriter::OnIdentify(CWdsVssWriter *this, struct IVssCreateWriterMetadata *a2)
{
  __int64 v3; // rdi
  unsigned __int16 *v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // r14d
  unsigned __int16 * near **v23; // r15
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  int v29; // [rsp+28h] [rbp-41h]
  char v30; // [rsp+38h] [rbp-31h]
  char v31; // [rsp+40h] [rbp-29h]
  char v32; // [rsp+48h] [rbp-21h]
  char v33; // [rsp+50h] [rbp-19h]
  __int64 v34; // [rsp+70h] [rbp+7h] BYREF
  __int64 v35; // [rsp+78h] [rbp+Fh] BYREF
  void *v36; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int16 *v37; // [rsp+88h] [rbp+1Fh] BYREF
  void *v38; // [rsp+D8h] [rbp+6Fh] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp+77h] BYREF
  BSTR v40; // [rsp+E8h] [rbp+7Fh] BYREF

  v38 = 0;
  LODWORD(v3) = 0;
  v4 = 0;
  if ( !a2 )
    return 0;
  v33 = 1;
  v32 = 1;
  v31 = 0;
  v30 = 0;
  LODWORD(v5) = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD, const wchar_t *, const wchar_t *, _QWORD, _DWORD, char, char, char, char, _DWORD))(*(_QWORD *)a2 + 16LL))(
                  a2,
                  2,
                  0,
                  L"WDSServer",
                  L"WDSServer",
                  0,
                  0,
                  v30,
                  v31,
                  v32,
                  v33,
                  0);
  if ( (int)ElValidateHr((unsigned int)v5, v6, v7, 293) >= 0 )
  {
    v36 = 0;
    v35 = 0;
    v34 = 0;
    v40 = 0;
    v37 = 0;
    bstrString = 0;
    v5 = CreateComObject(L"WdsMgmt.WdsManager", &GUID_f5c420af_ced9_4b92_809b_9debd7e32b03, &v36);
    if ( (unsigned int)ElValidateWin32_11(v5, v8, v9, 108) )
    {
      if ( (int)v5 > 0 )
        LODWORD(v5) = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v5 = (unsigned int)SysAllocStringHr(0, &bstrString);
      if ( (int)ElValidateHr(v5, v12, v13, 115) >= 0 )
      {
        v5 = (*(unsigned int (__fastcall **)(void *, BSTR, __int64 *))(*(_QWORD *)v36 + 56LL))(v36, bstrString, &v35);
        if ( (int)ElValidateHr(v5, v14, v15, 118) >= 0 )
        {
          v5 = (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 88LL))(v35, &v34);
          if ( (int)ElValidateHr(v5, v16, v17, 124) >= 0 )
          {
            v5 = (*(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v34 + 56LL))(v34, &v40);
            if ( (int)ElValidateHr(v5, v18, v19, 130) >= 0 )
            {
              v5 = (unsigned int)WcsDupHr(v40, &v37);
              if ( (int)ElValidateHr(v5, v20, v21, 136) >= 0 )
                v4 = v37;
            }
          }
        }
      }
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v40 )
    {
      SysFreeString(v40);
      v40 = 0;
    }
    if ( v34 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      v34 = 0;
    }
    if ( v35 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v35 = 0;
    }
    if ( v36 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
      v36 = 0;
    }
    if ( (int)v5 < 0 && v37 )
      WdsPrivateHpFree(v37);
    if ( (int)ElValidateHr((unsigned int)v5, v10, v11, 299) >= 0 )
    {
      v22 = 0;
      v23 = &g_WdsFoldersForBackup;
      while ( 1 )
      {
        v3 = (unsigned int)ConcatenatePaths(v4, *v23, &v38);
        if ( (unsigned int)ElValidateWin32_11(v3, v24, v25, 310) )
          break;
        LOBYTE(v29) = 1;
        v5 = (*(unsigned int (__fastcall **)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, void *, const wchar_t *, int, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
               a2,
               0,
               L"WDSServer",
               v38,
               L"*.*",
               v29,
               0,
               3855);
        if ( (int)ElValidateHr(v5, v26, v27, 321) >= 0 )
        {
          if ( v38 )
          {
            WdsPrivateHpFree(v38);
            v38 = 0;
          }
          ++v22;
          ++v23;
          if ( v22 < 5 )
            continue;
        }
        goto LABEL_36;
      }
      if ( (int)v3 > 0 )
        LODWORD(v5) = (unsigned __int16)v3 | 0x80070000;
      else
        LODWORD(v5) = v3;
    }
LABEL_36:
    if ( v4 )
      WdsPrivateHpFree(v4);
  }
  if ( v38 )
    WdsPrivateHpFree(v38);
  return (int)v5 >= 0 && (_DWORD)v3 == 0;
}

```

## disassembly

```asm
0x18001a910  mov     [rsp-8+arg_0], rbx
0x18001a915  push    rbp
0x18001a916  push    rsi
0x18001a917  push    rdi
0x18001a918  push    r12
0x18001a91a  push    r13
0x18001a91c  push    r14
0x18001a91e  push    r15
0x18001a920  lea     rbp, [rsp-27h]
0x18001a925  sub     rsp, 90h
0x18001a92c  xor     r13d, r13d
0x18001a92f  mov     r12, rdx
0x18001a932  mov     [rbp+57h+arg_8], r13
0x18001a936  mov     edi, r13d
0x18001a939  mov     esi, r13d
0x18001a93c  test    rdx, rdx
0x18001a93f  jz      loc_18001AC6A
0x18001a945  mov     rax, [rdx]
0x18001a948  lea     rcx, aWdsserver; "WDSServer"
0x18001a94f  mov     [rsp+0C0h+var_68], r13d
0x18001a954  lea     edx, [r13+2]
0x18001a958  mov     [rsp+0C0h+var_70], 1
0x18001a95d  mov     r9, rcx
0x18001a960  mov     [rsp+0C0h+var_78], 1
0x18001a965  xor     r8d, r8d
0x18001a968  mov     rax, [rax+10h]
0x18001a96c  mov     [rsp+0C0h+var_80], r13b
0x18001a971  mov     [rsp+0C0h+var_88], r13b
0x18001a976  mov     dword ptr [rsp+0C0h+var_90], r13d
0x18001a97b  mov     [rsp+0C0h+var_98], r13
0x18001a980  mov     [rsp+0C0h+var_A0], rcx
0x18001a985  mov     rcx, r12
0x18001a988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a98d  mov     r9d, 125h
0x18001a993  mov     ecx, eax
0x18001a995  mov     ebx, eax
0x18001a997  call    ElValidateHr
0x18001a99c  test    eax, eax
0x18001a99e  js      loc_18001AC4A
0x18001a9a4  lea     r8, [rbp+57h+var_40]
0x18001a9a8  mov     [rbp+57h+var_40], r13
0x18001a9ac  lea     rdx, _GUID_f5c420af_ced9_4b92_809b_9debd7e32b03
0x18001a9b3  mov     [rbp+57h+var_48], r13
0x18001a9b7  lea     rcx, aWdsmgmtWdsmana; "WdsMgmt.WdsManager"
0x18001a9be  mov     [rbp+57h+var_50], r13
0x18001a9c2  mov     [rbp+57h+arg_18], r13
0x18001a9c6  mov     [rbp+57h+var_38], r13
0x18001a9ca  mov     [rbp+57h+bstrString], r13
0x18001a9ce  call    cs:__imp_?CreateComObject@@YAKPEBGAEBU_GUID@@PEAPEAX@Z; CreateComObject(ushort const *,_GUID const &,void * *)
0x18001a9d5  nop     dword ptr [rax+rax+00h]
0x18001a9da  mov     ecx, eax
0x18001a9dc  lea     r9d, [r13+6Ch]
0x18001a9e0  mov     ebx, eax
0x18001a9e2  call    ElValidateWin32_11
0x18001a9e7  test    eax, eax
0x18001a9e9  jz      short loc_18001AA01
0x18001a9eb  test    ebx, ebx
0x18001a9ed  jle     loc_18001AACD
0x18001a9f3  movzx   ebx, bx
0x18001a9f6  or      ebx, 80070000h
0x18001a9fc  jmp     loc_18001AACD
0x18001aa01  lea     rdx, [rbp+57h+bstrString]
0x18001aa05  xor     ecx, ecx
0x18001aa07  call    cs:__imp_?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x18001aa0e  nop     dword ptr [rax+rax+00h]
0x18001aa13  mov     ecx, eax
0x18001aa15  mov     r9d, 73h ; 's'
0x18001aa1b  mov     ebx, eax
0x18001aa1d  call    ElValidateHr
0x18001aa22  test    eax, eax
0x18001aa24  js      loc_18001AACD
0x18001aa2a  mov     rcx, [rbp+57h+var_40]
0x18001aa2e  lea     r8, [rbp+57h+var_48]
0x18001aa32  mov     rdx, [rbp+57h+bstrString]
0x18001aa36  mov     rax, [rcx]
0x18001aa39  mov     rax, [rax+38h]
0x18001aa3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa42  mov     r9d, 76h ; 'v'
0x18001aa48  mov     ecx, eax
0x18001aa4a  mov     ebx, eax
0x18001aa4c  call    ElValidateHr
0x18001aa51  test    eax, eax
0x18001aa53  js      short loc_18001AACD
0x18001aa55  mov     rcx, [rbp+57h+var_48]
0x18001aa59  lea     rdx, [rbp+57h+var_50]
0x18001aa5d  mov     rax, [rcx]
0x18001aa60  mov     rax, [rax+58h]
0x18001aa64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa69  mov     r9d, 7Ch ; '|'
0x18001aa6f  mov     ecx, eax
0x18001aa71  mov     ebx, eax
0x18001aa73  call    ElValidateHr
0x18001aa78  test    eax, eax
0x18001aa7a  js      short loc_18001AACD
0x18001aa7c  mov     rcx, [rbp+57h+var_50]
0x18001aa80  lea     rdx, [rbp+57h+arg_18]
0x18001aa84  mov     rax, [rcx]
0x18001aa87  mov     rax, [rax+38h]
0x18001aa8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa90  mov     r9d, 82h
0x18001aa96  mov     ecx, eax
0x18001aa98  mov     ebx, eax
0x18001aa9a  call    ElValidateHr
0x18001aa9f  test    eax, eax
0x18001aaa1  js      short loc_18001AACD
0x18001aaa3  mov     rcx, [rbp+57h+arg_18]
0x18001aaa7  lea     rdx, [rbp+57h+var_38]
0x18001aaab  call    cs:__imp_?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x18001aab2  nop     dword ptr [rax+rax+00h]
0x18001aab7  mov     ecx, eax
0x18001aab9  mov     r9d, 88h
0x18001aabf  mov     ebx, eax
0x18001aac1  call    ElValidateHr
0x18001aac6  test    eax, eax
0x18001aac8  cmovns  rsi, [rbp+57h+var_38]
0x18001aacd  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001aad1  test    rcx, rcx
0x18001aad4  jz      short loc_18001AAE6
0x18001aad6  call    cs:__imp_SysFreeString
0x18001aadd  nop     dword ptr [rax+rax+00h]
0x18001aae2  mov     [rbp+57h+bstrString], r13
0x18001aae6  mov     rcx, [rbp+57h+arg_18]; bstrString
0x18001aaea  test    rcx, rcx
0x18001aaed  jz      short loc_18001AAFF
0x18001aaef  call    cs:__imp_SysFreeString
0x18001aaf6  nop     dword ptr [rax+rax+00h]
0x18001aafb  mov     [rbp+57h+arg_18], r13
0x18001aaff  mov     rcx, [rbp+57h+var_50]
0x18001ab03  test    rcx, rcx
0x18001ab06  jz      short loc_18001AB18
0x18001ab08  mov     rax, [rcx]
0x18001ab0b  mov     rax, [rax+10h]
0x18001ab0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab14  mov     [rbp+57h+var_50], r13
0x18001ab18  mov     rcx, [rbp+57h+var_48]
0x18001ab1c  test    rcx, rcx
0x18001ab1f  jz      short loc_18001AB31
0x18001ab21  mov     rax, [rcx]
0x18001ab24  mov     rax, [rax+10h]
0x18001ab28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab2d  mov     [rbp+57h+var_48], r13
0x18001ab31  mov     rcx, [rbp+57h+var_40]
0x18001ab35  test    rcx, rcx
0x18001ab38  jz      short loc_18001AB4A
0x18001ab3a  mov     rax, [rcx]
0x18001ab3d  mov     rax, [rax+10h]
0x18001ab41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab46  mov     [rbp+57h+var_40], r13
0x18001ab4a  test    ebx, ebx
0x18001ab4c  jns     short loc_18001AB63
0x18001ab4e  mov     rcx, [rbp+57h+var_38]
0x18001ab52  test    rcx, rcx
0x18001ab55  jz      short loc_18001AB63
0x18001ab57  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18001ab5e  nop     dword ptr [rax+rax+00h]
0x18001ab63  mov     r9d, 12Bh
0x18001ab69  mov     ecx, ebx
0x18001ab6b  call    ElValidateHr
0x18001ab70  test    eax, eax
0x18001ab72  js      loc_18001AC36
0x18001ab78  mov     r14d, r13d
0x18001ab7b  lea     r15, ?g_WdsFoldersForBackup@@3PAPEAGA; ushort * near * g_WdsFoldersForBackup
0x18001ab82  mov     rdx, [r15]
0x18001ab85  lea     r8, [rbp+57h+arg_8]
0x18001ab89  mov     rcx, rsi
0x18001ab8c  call    cs:__imp_ConcatenatePaths
0x18001ab93  nop     dword ptr [rax+rax+00h]
0x18001ab98  mov     ecx, eax
0x18001ab9a  mov     r9d, 136h
0x18001aba0  mov     edi, eax
0x18001aba2  call    ElValidateWin32_11
0x18001aba7  test    eax, eax
0x18001aba9  jnz     short loc_18001AC25
0x18001abab  mov     rcx, [r12]
0x18001abaf  lea     r8, aWdsserver; "WDSServer"
0x18001abb6  mov     r9, [rbp+57h+arg_8]
0x18001abba  xor     edx, edx
0x18001abbc  mov     dword ptr [rsp+0C0h+var_88], 0F0Fh
0x18001abc4  mov     [rsp+0C0h+var_90], r13
0x18001abc9  mov     rax, [rcx+28h]
0x18001abcd  lea     rcx, asc_180022E80; "*.*"
0x18001abd4  mov     byte ptr [rsp+0C0h+var_98], 1
0x18001abd9  mov     [rsp+0C0h+var_A0], rcx
0x18001abde  mov     rcx, r12
0x18001abe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abe6  mov     r9d, 141h
0x18001abec  mov     ecx, eax
0x18001abee  mov     ebx, eax
0x18001abf0  call    ElValidateHr
0x18001abf5  test    eax, eax
0x18001abf7  js      short loc_18001AC36
0x18001abf9  mov     rcx, [rbp+57h+arg_8]
0x18001abfd  test    rcx, rcx
0x18001ac00  jz      short loc_18001AC12
0x18001ac02  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18001ac09  nop     dword ptr [rax+rax+00h]
0x18001ac0e  mov     [rbp+57h+arg_8], r13
0x18001ac12  inc     r14d
0x18001ac15  add     r15, 8
0x18001ac19  cmp     r14d, 5
0x18001ac1d  jb      loc_18001AB82
0x18001ac23  jmp     short loc_18001AC36
0x18001ac25  test    edi, edi
0x18001ac27  jg      short loc_18001AC2D
0x18001ac29  mov     ebx, edi
0x18001ac2b  jmp     short loc_18001AC36
0x18001ac2d  movzx   ebx, di
0x18001ac30  or      ebx, 80070000h
0x18001ac36  test    rsi, rsi
0x18001ac39  jz      short loc_18001AC4A
0x18001ac3b  mov     rcx, rsi
0x18001ac3e  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18001ac45  nop     dword ptr [rax+rax+00h]
0x18001ac4a  mov     rcx, [rbp+57h+arg_8]
0x18001ac4e  test    rcx, rcx
0x18001ac51  jz      short loc_18001AC5F
0x18001ac53  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18001ac5a  nop     dword ptr [rax+rax+00h]
0x18001ac5f  test    ebx, ebx
0x18001ac61  js      short loc_18001AC6A
0x18001ac63  test    edi, edi
0x18001ac65  setz    al
0x18001ac68  jmp     short loc_18001AC6C
0x18001ac6a  xor     al, al
0x18001ac6c  mov     rbx, [rsp+0C0h+arg_0]
0x18001ac74  add     rsp, 90h
0x18001ac7b  pop     r15
0x18001ac7d  pop     r14
0x18001ac7f  pop     r13
0x18001ac81  pop     r12
0x18001ac83  pop     rdi
0x18001ac84  pop     rsi
0x18001ac85  pop     rbp
0x18001ac86  retn
```
