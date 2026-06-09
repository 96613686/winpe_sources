# _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)

- ea: `0x180004ec0`
- end: `0x180005391`
- name: `?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z`
- size: `1233`
- prototype: `__int64 __fastcall(const WCHAR *, WCHAR *, int, char, char, const WCHAR *lpString1)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800045a8`
- `0x180046178`

## callees

- `0x180004ec0`
- `0x180006794`
- `0x18000da00`
- `0x18003d244`
- `0x180054130`
- `0x180054ad4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180004f97`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005317`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180004f97`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005317`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005060`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800052e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005060`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800052e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005228`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005228`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052fa`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005155`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000526b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005155`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000526b`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800051c9`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800051c9`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004f6b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004f6b`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180004fbe`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180004fbe`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000520d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000520d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800052ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800052ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800051a8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800051a8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000529a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000529a`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall _AppendPathAndCreateFolder(
        const WCHAR *a1,
        WCHAR *a2,
        int a3,
        char a4,
        char a5,
        const WCHAR *lpString1)
{
  WCHAR *v6; // r11
  __int64 v7; // r12
  __int64 v8; // r15
  __int64 v9; // rsi
  __int64 v12; // rcx
  const WCHAR *v13; // r10
  __int64 v14; // r9
  WCHAR *v15; // rcx
  HRESULT Error; // edi
  wchar_t *i; // rax
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rax
  __int64 v21; // rcx
  WCHAR *v22; // rdx
  __int64 v23; // r8
  WCHAR *v24; // r9
  WCHAR *v25; // rcx
  const wchar_t *v26; // rdx
  WCHAR *v27; // rax
  WCHAR *v28; // rcx
  void *v29; // rax
  void *v30; // rbx
  bool v31; // si
  size_t v32; // rax
  LPWSTR v33; // r9
  DWORD nLengthNeeded[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp+170h] BYREF

  v6 = pszPath;
  v7 = a3;
  v8 = 2147483646;
  v9 = 260;
  StringSecurityDescriptor = a2;
  v12 = 2147483646;
  v13 = lpString1;
  v14 = 260;
  do
  {
    if ( !v12 )
      break;
    if ( !*v13 )
      break;
    *v6++ = *v13++;
    --v12;
    --v14;
  }
  while ( v14 );
  v15 = v6 - 1;
  Error = -2147024774;
  if ( v14 )
  {
    v15 = v6;
    Error = 0;
  }
  *v15 = 0;
  if ( v14 )
  {
    Error = PathCchAppend(pszPath, 0x104u, a1);
    if ( Error >= 0 )
    {
      for ( i = wcsstr(pszPath, L"/"); i; i = wcsstr(i, L"/") )
        *i = 92;
      Error = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
      if ( Error >= 0 )
      {
        v18 = -1;
        do
          ++v18;
        while ( lpString1[v18] );
        if ( v18 > 0xFFFFFFFF )
          return (unsigned int)-2147024362;
        v19 = -1;
        do
          ++v19;
        while ( pszPathOut[v19] );
        if ( v19 > 0xFFFFFFFF )
          return (unsigned int)-2147024362;
        Error = -2147024809;
        if ( (unsigned int)v19 > (unsigned int)v18
          && CompareStringOrdinal(lpString1, v18, pszPathOut, v18, 0) == 2
          && pszPathOut[(unsigned int)v18] == 92 )
        {
          v21 = 2147483646;
          v22 = pszPathOut;
          v23 = 260;
          v24 = (WCHAR *)lpString1;
          do
          {
            if ( !v21 )
              break;
            if ( !*v22 )
              break;
            *v24++ = *v22++;
            --v21;
            --v23;
          }
          while ( v23 );
          v25 = v24 - 1;
          Error = -2147024774;
          if ( v23 )
          {
            v25 = v24;
            Error = 0;
          }
          *v25 = 0;
          if ( v23 && a5 )
          {
            if ( (_DWORD)v7 )
            {
              v33 = L"BU";
              if ( (a4 & 1) == 0 )
                v33 = StringSecurityDescriptor;
              Error = StringCchPrintfW(pszPathOut, 0x104u, (&off_1800EE010)[3 * v7], v33);
            }
            else
            {
              v26 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
              v27 = pszPathOut;
              do
              {
                if ( !v8 )
                  break;
                if ( !*v26 )
                  break;
                *v27++ = *v26++;
                --v8;
                --v9;
              }
              while ( v9 );
              v28 = v27 - 1;
              Error = -2147024774;
              if ( v9 )
              {
                v28 = v27;
                Error = 0;
              }
              *v28 = 0;
            }
            if ( Error >= 0 )
            {
              nLengthNeeded[0] = 0;
              if ( GetFileSecurityW(lpString1, 7u, 0, 0, nLengthNeeded) )
                goto LABEL_42;
              if ( (unsigned int)ResultFromKnownLastError() != -2147024774 )
                goto LABEL_42;
              v29 = CoTaskMemAlloc(nLengthNeeded[0]);
              v30 = v29;
              if ( !v29 )
                goto LABEL_42;
              v31 = 0;
              v32 = CTCoAllocPolicy::_CoTaskMemSize(v29);
              memset_0(v30, 0, v32);
              if ( GetFileSecurityW(lpString1, 7u, v30, nLengthNeeded[0], nLengthNeeded) )
              {
                StringSecurityDescriptor = 0;
                if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v30, 1u, 7u, &StringSecurityDescriptor, 0) )
                {
                  v31 = CompareStringOrdinal(StringSecurityDescriptor, -1, pszPathOut, -1, 1) == 2;
                  LocalFree(StringSecurityDescriptor);
                }
              }
              CoTaskMemFree(v30);
              if ( !v31 )
              {
LABEL_42:
                *(_QWORD *)nLengthNeeded = 0;
                if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                       pszPathOut,
                       1u,
                       (PSECURITY_DESCRIPTOR *)nLengthNeeded,
                       0)
                  || (Error = ResultFromKnownLastError(), Error >= 0) )
                {
                  if ( SetFileSecurityW(lpString1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
                    goto LABEL_46;
                  Error = ResultFromKnownLastError();
                  if ( Error != -2147024894 )
                  {
                    if ( Error == -2147024891 )
                      Error = 0;
                    goto LABEL_47;
                  }
                  SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
                  *(_QWORD *)&SecurityAttributes.nLength = 24;
                  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                  if ( CreateDirectoryW(lpString1, &SecurityAttributes) )
LABEL_46:
                    Error = 0;
                  else
                    Error = ResultFromKnownLastError();
LABEL_47:
                  LocalFree(*(HLOCAL *)nLengthNeeded);
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180004ec0  push    rbp
0x180004ec2  push    rsi
0x180004ec3  push    rdi
0x180004ec4  push    r12
0x180004ec6  push    r13
0x180004ec8  push    r14
0x180004eca  push    r15
0x180004ecc  lea     rbp, [rsp-390h]
0x180004ed4  sub     rsp, 490h
0x180004edb  mov     rax, cs:__security_cookie
0x180004ee2  xor     rax, rsp
0x180004ee5  mov     [rbp+3C0h+var_40], rax
0x180004eec  mov     r14, [rbp+3C0h+lpString1]
0x180004ef3  lea     r11, [rbp+3C0h+pszPath]
0x180004efa  movsxd  r12, r8d
0x180004efd  mov     r15d, 7FFFFFFEh
0x180004f03  mov     esi, 104h
0x180004f08  mov     [rsp+4C0h+StringSecurityDescriptor], rdx
0x180004f0d  mov     r8, rcx; pszMore
0x180004f10  mov     r13d, r9d
0x180004f13  mov     ecx, r15d
0x180004f16  mov     r10, r14
0x180004f19  mov     r9d, esi
0x180004f1c  nop     dword ptr [rax+00h]
0x180004f20  test    rcx, rcx
0x180004f23  jz      short loc_180004F43
0x180004f25  movzx   eax, word ptr [r10]
0x180004f29  test    ax, ax
0x180004f2c  jz      short loc_180004F43
0x180004f2e  mov     [r11], ax
0x180004f32  add     r10, 2
0x180004f36  add     r11, 2
0x180004f3a  dec     rcx
0x180004f3d  sub     r9, 1
0x180004f41  jnz     short loc_180004F20
0x180004f43  xor     eax, eax
0x180004f45  lea     rcx, [r11-2]
0x180004f49  test    r9, r9
0x180004f4c  mov     edi, 8007007Ah
0x180004f51  cmovnz  rcx, r11
0x180004f55  cmovnz  edi, eax
0x180004f58  mov     [rcx], ax
0x180004f5b  jz      loc_18000501D
0x180004f61  mov     rdx, rsi; cchPath
0x180004f64  lea     rcx, [rbp+3C0h+pszPath]; pszPath
0x180004f6b  call    cs:__imp_PathCchAppend
0x180004f72  nop     dword ptr [rax+rax+00h]
0x180004f77  mov     edi, eax
0x180004f79  test    eax, eax
0x180004f7b  js      loc_18000501D
0x180004f81  lea     rdx, SubStr; "/"
0x180004f88  mov     [rsp+4C0h+arg_10], rbx
0x180004f90  lea     rcx, [rbp+3C0h+pszPath]; Str
0x180004f97  call    cs:__imp_wcsstr
0x180004f9e  nop     dword ptr [rax+rax+00h]
0x180004fa3  test    rax, rax
0x180004fa6  jnz     loc_180005308
0x180004fac  xor     r9d, r9d; dwFlags
0x180004faf  lea     r8, [rbp+3C0h+pszPath]; pszPathIn
0x180004fb6  mov     rdx, rsi; cchPathOut
0x180004fb9  lea     rcx, [rsp+4C0h+pszPathOut]; pszPathOut
0x180004fbe  call    cs:__imp_PathCchCanonicalizeEx
0x180004fc5  nop     dword ptr [rax+rax+00h]
0x180004fca  mov     edi, eax
0x180004fcc  test    eax, eax
0x180004fce  js      short loc_180005015
0x180004fd0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180004fd7  nop     word ptr [rax+rax+00000000h]
0x180004fe0  inc     rbx
0x180004fe3  cmp     word ptr [r14+rbx*2], 0
0x180004fe9  jnz     short loc_180004FE0
0x180004feb  mov     edx, 0FFFFFFFFh
0x180004ff0  cmp     rbx, rdx
0x180004ff3  ja      short loc_180005010
0x180004ff5  lea     rcx, [rsp+4C0h+pszPathOut]
0x180004ffa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005001  inc     rax
0x180005004  cmp     word ptr [rcx+rax*2], 0
0x180005009  jnz     short loc_180005001
0x18000500b  cmp     rax, rdx
0x18000500e  jbe     short loc_180005042
0x180005010  mov     edi, 80070216h
0x180005015  mov     rbx, [rsp+4C0h+arg_10]
0x18000501d  mov     eax, edi
0x18000501f  mov     rcx, [rbp+3C0h+var_40]
0x180005026  xor     rcx, rsp; StackCookie
0x180005029  call    __security_check_cookie
0x18000502e  add     rsp, 490h
0x180005035  pop     r15
0x180005037  pop     r14
0x180005039  pop     r13
0x18000503b  pop     r12
0x18000503d  pop     rdi
0x18000503e  pop     rsi
0x18000503f  pop     rbp
0x180005040  retn
0x180005042  mov     edi, 80070057h
0x180005047  cmp     eax, ebx
0x180005049  jbe     short loc_180005015
0x18000504b  mov     r9d, ebx; cchCount2
0x18000504e  mov     [rsp+4C0h+bIgnoreCase], 0; bIgnoreCase
0x180005056  lea     r8, [rsp+4C0h+pszPathOut]; lpString2
0x18000505b  mov     edx, ebx; cchCount1
0x18000505d  mov     rcx, r14; lpString1
0x180005060  call    cs:__imp_CompareStringOrdinal
0x180005067  nop     dword ptr [rax+rax+00h]
0x18000506c  cmp     eax, 2
0x18000506f  jnz     short loc_180005015
0x180005071  mov     eax, ebx
0x180005073  cmp     [rsp+rax*2+4C0h+pszPathOut], 5Ch ; '\'
0x180005079  jnz     short loc_180005015
0x18000507b  mov     rcx, r15
0x18000507e  lea     rdx, [rsp+4C0h+pszPathOut]
0x180005083  mov     r8, rsi
0x180005086  mov     r9, r14
0x180005089  nop     dword ptr [rax+00000000h]
0x180005090  test    rcx, rcx
0x180005093  jz      short loc_1800050B2
0x180005095  movzx   eax, word ptr [rdx]
0x180005098  test    ax, ax
0x18000509b  jz      short loc_1800050B2
0x18000509d  mov     [r9], ax
0x1800050a1  add     rdx, 2
0x1800050a5  add     r9, 2
0x1800050a9  dec     rcx
0x1800050ac  sub     r8, 1
0x1800050b0  jnz     short loc_180005090
0x1800050b2  xor     eax, eax
0x1800050b4  lea     rcx, [r9-2]
0x1800050b8  test    r8, r8
0x1800050bb  mov     edi, 8007007Ah
0x1800050c0  cmovnz  rcx, r9
0x1800050c4  cmovnz  edi, eax
0x1800050c7  mov     [rcx], ax
0x1800050ca  jz      loc_180005015
0x1800050d0  cmp     [rbp+3C0h+arg_20], al
0x1800050d6  jz      loc_180005015
0x1800050dc  test    r12d, r12d
0x1800050df  jnz     loc_18000532D
0x1800050e5  mov     rdx, cs:off_1800EE010; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x1800050ec  lea     rax, [rsp+4C0h+pszPathOut]
0x1800050f1  test    r15, r15
0x1800050f4  jz      short loc_180005112
0x1800050f6  movzx   ecx, word ptr [rdx]
0x1800050f9  test    cx, cx
0x1800050fc  jz      short loc_180005112
0x1800050fe  mov     [rax], cx
0x180005101  add     rdx, 2
0x180005105  add     rax, 2
0x180005109  dec     r15
0x18000510c  sub     rsi, 1
0x180005110  jnz     short loc_1800050F1
0x180005112  test    rsi, rsi
0x180005115  lea     rcx, [rax-2]
0x180005119  mov     edi, 8007007Ah
0x18000511e  cmovnz  rcx, rax
0x180005122  xor     eax, eax
0x180005124  test    rsi, rsi
0x180005127  cmovnz  edi, eax
0x18000512a  mov     [rcx], ax
0x18000512d  test    edi, edi
0x18000512f  js      loc_180005015
0x180005135  lea     rax, [rsp+4C0h+nLengthNeeded]
0x18000513a  mov     [rsp+4C0h+nLengthNeeded], 0
0x180005142  xor     r9d, r9d; nLength
0x180005145  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax; lpnLengthNeeded
0x18000514a  xor     r8d, r8d; pSecurityDescriptor
0x18000514d  mov     edx, 7; RequestedInformation
0x180005152  mov     rcx, r14; lpFileName
0x180005155  call    cs:__imp_GetFileSecurityW
0x18000515c  nop     dword ptr [rax+rax+00h]
0x180005161  test    eax, eax
0x180005163  jnz     short loc_18000518D
0x180005165  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000516a  cmp     eax, 8007007Ah
0x18000516f  jnz     short loc_18000518D
0x180005171  mov     ecx, [rsp+4C0h+nLengthNeeded]; cb
0x180005175  call    cs:__imp_CoTaskMemAlloc
0x18000517c  nop     dword ptr [rax+rax+00h]
0x180005181  mov     rbx, rax
0x180005184  test    rax, rax
0x180005187  jnz     loc_180005239
0x18000518d  xor     r9d, r9d; SecurityDescriptorSize
0x180005190  mov     qword ptr [rsp+4C0h+nLengthNeeded], 0
0x180005199  lea     r8, [rsp+4C0h+nLengthNeeded]; SecurityDescriptor
0x18000519e  mov     edx, 1; StringSDRevision
0x1800051a3  lea     rcx, [rsp+4C0h+pszPathOut]; StringSecurityDescriptor
0x1800051a8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800051af  nop     dword ptr [rax+rax+00h]
0x1800051b4  test    eax, eax
0x1800051b6  jz      loc_180005361
0x1800051bc  mov     r8, qword ptr [rsp+4C0h+nLengthNeeded]; pSecurityDescriptor
0x1800051c1  mov     edx, 7; SecurityInformation
0x1800051c6  mov     rcx, r14; lpFileName
0x1800051c9  call    cs:__imp_SetFileSecurityW
0x1800051d0  nop     dword ptr [rax+rax+00h]
0x1800051d5  test    eax, eax
0x1800051d7  jnz     short loc_180005221
0x1800051d9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800051de  mov     edi, eax
0x1800051e0  cmp     eax, 80070002h
0x1800051e5  jnz     loc_180005381
0x1800051eb  mov     rax, qword ptr [rsp+4C0h+nLengthNeeded]
0x1800051f0  lea     rdx, [rsp+4C0h+SecurityAttributes]; lpSecurityAttributes
0x1800051f5  mov     [rsp+4C0h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800051fa  mov     rcx, r14; lpPathName
0x1800051fd  xor     eax, eax
0x1800051ff  mov     qword ptr [rsp+4C0h+SecurityAttributes.nLength], 18h
0x180005208  mov     qword ptr [rsp+4C0h+SecurityAttributes.bInheritHandle], rax
0x18000520d  call    cs:__imp_CreateDirectoryW
0x180005214  nop     dword ptr [rax+rax+00h]
0x180005219  test    eax, eax
0x18000521b  jz      loc_180005375
0x180005221  xor     edi, edi
0x180005223  mov     rcx, qword ptr [rsp+4C0h+nLengthNeeded]; hMem
0x180005228  call    cs:__imp_LocalFree
0x18000522f  nop     dword ptr [rax+rax+00h]
0x180005234  jmp     loc_180005015
0x180005239  mov     rcx, rbx; void *
0x18000523c  xor     sil, sil
0x18000523f  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180005244  mov     r8, rax; Size
0x180005247  xor     edx, edx; Val
0x180005249  mov     rcx, rbx; void *
0x18000524c  call    memset_0
0x180005251  mov     r9d, [rsp+4C0h+nLengthNeeded]; nLength
0x180005256  lea     rax, [rsp+4C0h+nLengthNeeded]
0x18000525b  mov     r8, rbx; pSecurityDescriptor
0x18000525e  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax; lpnLengthNeeded
0x180005263  mov     edx, 7; RequestedInformation
0x180005268  mov     rcx, r14; lpFileName
0x18000526b  call    cs:__imp_GetFileSecurityW
0x180005272  nop     dword ptr [rax+rax+00h]
0x180005277  test    eax, eax
0x180005279  jz      short loc_1800052AA
0x18000527b  xor     eax, eax
0x18000527d  lea     r9, [rsp+4C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180005282  mov     edx, 1; RequestedStringSDRevision
0x180005287  mov     [rsp+4C0h+StringSecurityDescriptor], rax
0x18000528c  mov     r8d, 7; SecurityInformation
0x180005292  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax; StringSecurityDescriptorLen
0x180005297  mov     rcx, rbx; SecurityDescriptor
0x18000529a  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800052a1  nop     dword ptr [rax+rax+00h]
0x1800052a6  test    eax, eax
0x1800052a8  jnz     short loc_1800052C7
0x1800052aa  mov     rcx, rbx; pv
0x1800052ad  call    cs:__imp_CoTaskMemFree
0x1800052b4  nop     dword ptr [rax+rax+00h]
0x1800052b9  test    sil, sil
0x1800052bc  jnz     loc_180005015
0x1800052c2  jmp     loc_18000518D
0x1800052c7  mov     rcx, [rsp+4C0h+StringSecurityDescriptor]; lpString1
0x1800052cc  lea     r8, [rsp+4C0h+pszPathOut]; lpString2
0x1800052d1  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800052d7  mov     [rsp+4C0h+bIgnoreCase], 1; bIgnoreCase
0x1800052df  mov     edx, r9d; cchCount1
0x1800052e2  call    cs:__imp_CompareStringOrdinal
0x1800052e9  nop     dword ptr [rax+rax+00h]
0x1800052ee  mov     rcx, [rsp+4C0h+StringSecurityDescriptor]; hMem
0x1800052f3  cmp     eax, 2
0x1800052f6  setz    sil
0x1800052fa  call    cs:__imp_LocalFree
0x180005301  nop     dword ptr [rax+rax+00h]
0x180005306  jmp     short loc_1800052AA
0x180005308  lea     rdx, SubStr; "/"
0x18000530f  mov     word ptr [rax], 5Ch ; '\'
0x180005314  mov     rcx, rax; Str
0x180005317  call    cs:__imp_wcsstr
0x18000531e  nop     dword ptr [rax+rax+00h]
0x180005323  test    rax, rax
0x180005326  jnz     short loc_180005308
0x180005328  jmp     loc_180004FAC
0x18000532d  test    r13b, 1
0x180005331  lea     rax, off_1800EE010; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x180005338  lea     r9, aBu; "BU"
0x18000533f  mov     rdx, rsi; unsigned __int64
0x180005342  cmovz   r9, [rsp+4C0h+StringSecurityDescriptor]
0x180005348  lea     r8, [r12+r12*2]
0x18000534c  mov     r8, [rax+r8*8]; unsigned __int16 *
0x180005350  lea     rcx, [rsp+4C0h+pszPathOut]; unsigned __int16 *
0x180005355  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000535a  mov     edi, eax
0x18000535c  jmp     loc_18000512D
0x180005361  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005366  mov     edi, eax
0x180005368  test    eax, eax
0x18000536a  js      loc_180005015
0x180005370  jmp     loc_1800051BC
0x180005375  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000537a  mov     edi, eax
0x18000537c  jmp     loc_180005223
0x180005381  xor     eax, eax
0x180005383  cmp     edi, 80070005h
0x180005389  cmovz   edi, eax
0x18000538c  jmp     loc_180005223
```
