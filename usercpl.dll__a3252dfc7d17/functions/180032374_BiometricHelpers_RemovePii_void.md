# BiometricHelpers::RemovePii(void *)

- ea: `0x180032374`
- end: `0x1800325be`
- name: `?RemovePii@BiometricHelpers@@SAXPEAX@Z`
- size: `586`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800343b0`

## callees

- `0x180032374`
- `0x18007728a`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800323af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800323af`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180032598`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180032598`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800323cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800323e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032403`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003241f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003243b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032457`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800323cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800323e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032403`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003241f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003243b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032457`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800324a0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800324a0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180032486`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180032486`

## string_xrefs

- `0x1800323c1`: `WinBioRemoveCredential`
- `0x1800323a2`: `winbio.dll`
- `0x1800323dd`: `WinBioOpenSession`
- `0x180032415`: `WinBioDeleteTemplate`

## pseudocode

```c
void __fastcall BiometricHelpers::RemovePii(void *a1)
{
  HMODULE Library; // rax
  HMODULE v2; // rdi
  FARPROC ProcAddress; // rsi
  FARPROC v4; // r13
  FARPROC v5; // rbx
  FARPROC v6; // r12
  FARPROC v7; // r14
  FARPROC v8; // r15
  __int64 v9; // r9
  unsigned int *v10; // rbx
  char *v11; // rsi
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  PSID pSourceSid; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v15[3]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v16[2]; // [rsp+90h] [rbp-70h]
  _OWORD pDestinationSid[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v18[28]; // [rsp+E0h] [rbp-20h]

  pSourceSid = a1;
  Library = LoadLibraryExW(L"winbio.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WinBioRemoveCredential");
    if ( ProcAddress )
    {
      v4 = GetProcAddress(v2, "WinBioOpenSession");
      if ( v4 )
      {
        v5 = GetProcAddress(v2, "WinBioEnumBiometricUnits");
        if ( v5 )
        {
          v6 = GetProcAddress(v2, "WinBioDeleteTemplate");
          if ( v6 )
          {
            v7 = GetProcAddress(v2, "WinBioCloseSession");
            if ( v7 )
            {
              v8 = GetProcAddress(v2, "WinBioFree");
              if ( v8 )
              {
                memset_0(pDestinationSid, 0, 0x4Cu);
                if ( CopySid(0x44u, (char *)pDestinationSid + 8, pSourceSid) )
                {
                  LODWORD(pDestinationSid[0]) = 3;
                  DWORD1(pDestinationSid[0]) = GetLengthSid(pSourceSid);
                  v15[0] = pDestinationSid[0];
                  v15[2] = pDestinationSid[2];
                  v15[1] = pDestinationSid[1];
                  v16[0] = *(_OWORD *)v18;
                  *(_OWORD *)((char *)v16 + 12) = *(_OWORD *)&v18[12];
                  ((void (__fastcall *)(_OWORD *, __int64))ProcAddress)(v15, 1);
                  v12 = 0;
                  if ( ((int (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, __int64, unsigned int *))v4)(
                         8,
                         1,
                         0,
                         0,
                         0,
                         1,
                         &v12) >= 0 )
                  {
                    v14 = 0;
                    pSourceSid = 0;
                    if ( ((int (__fastcall *)(__int64, PSID *, __int64 *))v5)(8, &pSourceSid, &v14) >= 0 )
                    {
                      v10 = (unsigned int *)pSourceSid;
                      v11 = (char *)pSourceSid + 2588 * v14;
                      if ( pSourceSid != v11 )
                      {
                        do
                        {
                          if ( v10[1] == 1 )
                          {
                            LOBYTE(v9) = -1;
                            ((void (__fastcall *)(_QWORD, _QWORD, _OWORD *, __int64))v6)(v12, *v10, pDestinationSid, v9);
                          }
                          v10 += 647;
                        }
                        while ( v10 != (unsigned int *)v11 );
                        v10 = (unsigned int *)pSourceSid;
                      }
                      ((void (__fastcall *)(unsigned int *))v8)(v10);
                    }
                    ((void (__fastcall *)(_QWORD))v7)(v12);
                  }
                }
              }
            }
          }
        }
      }
    }
    FreeLibrary(v2);
  }
}

```

## disassembly

```asm
0x180032374  push    rbp
0x180032376  push    rbx
0x180032377  push    rsi
0x180032378  push    rdi
0x180032379  push    r12
0x18003237b  push    r13
0x18003237d  push    r14
0x18003237f  push    r15
0x180032381  lea     rbp, [rsp-18h]
0x180032386  sub     rsp, 118h
0x18003238d  mov     rax, cs:__security_cookie
0x180032394  xor     rax, rsp
0x180032397  mov     [rbp+50h+var_50], rax
0x18003239b  mov     [rsp+150h+pSourceSid], rcx
0x1800323a0  xor     edx, edx; hFile
0x1800323a2  lea     rcx, LibFileName; "winbio.dll"
0x1800323a9  mov     r8d, 800h; dwFlags
0x1800323af  call    cs:__imp_LoadLibraryExW
0x1800323b5  mov     rdi, rax
0x1800323b8  test    rax, rax
0x1800323bb  jz      loc_18003259E
0x1800323c1  lea     rdx, aWinbioremovecr; "WinBioRemoveCredential"
0x1800323c8  mov     rcx, rax; hModule
0x1800323cb  call    cs:__imp_GetProcAddress
0x1800323d1  mov     rsi, rax
0x1800323d4  test    rax, rax
0x1800323d7  jz      loc_180032595
0x1800323dd  lea     rdx, aWinbioopensess; "WinBioOpenSession"
0x1800323e4  mov     rcx, rdi; hModule
0x1800323e7  call    cs:__imp_GetProcAddress
0x1800323ed  mov     r13, rax
0x1800323f0  test    rax, rax
0x1800323f3  jz      loc_180032595
0x1800323f9  lea     rdx, aWinbioenumbiom; "WinBioEnumBiometricUnits"
0x180032400  mov     rcx, rdi; hModule
0x180032403  call    cs:__imp_GetProcAddress
0x180032409  mov     rbx, rax
0x18003240c  test    rax, rax
0x18003240f  jz      loc_180032595
0x180032415  lea     rdx, aWinbiodeletete; "WinBioDeleteTemplate"
0x18003241c  mov     rcx, rdi; hModule
0x18003241f  call    cs:__imp_GetProcAddress
0x180032425  mov     r12, rax
0x180032428  test    rax, rax
0x18003242b  jz      loc_180032595
0x180032431  lea     rdx, aWinbiocloseses; "WinBioCloseSession"
0x180032438  mov     rcx, rdi; hModule
0x18003243b  call    cs:__imp_GetProcAddress
0x180032441  mov     r14, rax
0x180032444  test    rax, rax
0x180032447  jz      loc_180032595
0x18003244d  lea     rdx, aWinbiofree; "WinBioFree"
0x180032454  mov     rcx, rdi; hModule
0x180032457  call    cs:__imp_GetProcAddress
0x18003245d  mov     r15, rax
0x180032460  test    rax, rax
0x180032463  jz      loc_180032595
0x180032469  xor     edx, edx; Val
0x18003246b  lea     rcx, [rbp+50h+pDestinationSid]; void *
0x18003246f  lea     r8d, [rdx+4Ch]; Size
0x180032473  call    memset_0
0x180032478  mov     r8, [rsp+150h+pSourceSid]; pSourceSid
0x18003247d  lea     rdx, [rbp+50h+pDestinationSid+8]; pDestinationSid
0x180032481  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180032486  call    cs:__imp_CopySid
0x18003248c  test    eax, eax
0x18003248e  jz      loc_180032595
0x180032494  mov     rcx, [rsp+150h+pSourceSid]; pSid
0x180032499  mov     dword ptr [rbp+50h+pDestinationSid], 3
0x1800324a0  call    cs:__imp_GetLengthSid
0x1800324a6  movaps  xmm1, [rbp+50h+var_90]
0x1800324aa  lea     rcx, [rsp+150h+var_F0]
0x1800324af  mov     dword ptr [rbp+50h+pDestinationSid+4], eax
0x1800324b2  mov     edx, 1
0x1800324b7  movaps  xmm0, [rbp+50h+pDestinationSid]
0x1800324bb  mov     rax, rsi
0x1800324be  movaps  [rsp+150h+var_F0], xmm0
0x1800324c3  movaps  xmm0, [rbp+50h+var_80]
0x1800324c7  movaps  [rbp+50h+var_D0], xmm0
0x1800324cb  movups  xmm0, [rbp+50h+var_64]
0x1800324cf  movaps  [rsp+150h+var_E0], xmm1
0x1800324d4  movaps  xmm1, xmmword ptr [rbp-20h]
0x1800324d8  movaps  xmmword ptr [rbp+50h+var_C0], xmm1
0x1800324dc  movups  xmmword ptr [rbp+50h+var_C0+0Ch], xmm0
0x1800324e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324e5  xor     esi, esi
0x1800324e7  lea     rax, [rsp+150h+var_110]
0x1800324ec  mov     [rsp+150h+var_120], rax
0x1800324f1  xor     r9d, r9d
0x1800324f4  xor     r8d, r8d
0x1800324f7  mov     [rsp+150h+var_110], esi
0x1800324fb  lea     eax, [rsi+1]
0x1800324fe  mov     [rsp+150h+var_128], rax
0x180032503  lea     ecx, [rsi+8]
0x180032506  mov     edx, eax
0x180032508  mov     [rsp+150h+var_130], rsi
0x18003250d  mov     rax, r13
0x180032510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032515  test    eax, eax
0x180032517  js      short loc_180032595
0x180032519  lea     r8, [rsp+150h+var_100]
0x18003251e  mov     [rsp+150h+var_100], rsi
0x180032523  lea     rdx, [rsp+150h+pSourceSid]
0x180032528  mov     [rsp+150h+pSourceSid], rsi
0x18003252d  lea     ecx, [rsi+8]
0x180032530  mov     rax, rbx
0x180032533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032538  test    eax, eax
0x18003253a  js      short loc_180032589
0x18003253c  imul    rsi, [rsp+150h+var_100], 0A1Ch
0x180032545  mov     rbx, [rsp+150h+pSourceSid]
0x18003254a  add     rsi, rbx
0x18003254d  cmp     rbx, rsi
0x180032550  jz      short loc_18003257E
0x180032552  cmp     dword ptr [rbx+4], 1
0x180032556  jnz     short loc_18003256D
0x180032558  mov     edx, [rbx]
0x18003255a  lea     r8, [rbp+50h+pDestinationSid]
0x18003255e  mov     ecx, [rsp+150h+var_110]
0x180032562  mov     r9b, 0FFh
0x180032565  mov     rax, r12
0x180032568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003256d  add     rbx, 0A1Ch
0x180032574  cmp     rbx, rsi
0x180032577  jnz     short loc_180032552
0x180032579  mov     rbx, [rsp+150h+pSourceSid]
0x18003257e  mov     rcx, rbx
0x180032581  mov     rax, r15
0x180032584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032589  mov     ecx, [rsp+150h+var_110]
0x18003258d  mov     rax, r14
0x180032590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032595  mov     rcx, rdi; hLibModule
0x180032598  call    cs:__imp_FreeLibrary
0x18003259e  mov     rcx, [rbp+50h+var_50]
0x1800325a2  xor     rcx, rsp; StackCookie
0x1800325a5  call    __security_check_cookie
0x1800325aa  add     rsp, 118h
0x1800325b1  pop     r15
0x1800325b3  pop     r14
0x1800325b5  pop     r13
0x1800325b7  pop     r12
0x1800325b9  pop     rdi
0x1800325ba  pop     rsi
0x1800325bb  pop     rbx
0x1800325bc  pop     rbp
0x1800325bd  retn
```
