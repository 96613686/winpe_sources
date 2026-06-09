# CGlobalThumbsDBStore::_CanWrite(IShellItem2 *)

- ea: `0x180044a74`
- end: `0x180044c1d`
- name: `?_CanWrite@CGlobalThumbsDBStore@@AEAAHPEAUIShellItem2@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(CGlobalThumbsDBStore *__hidden this, struct IShellItem2 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800443fc`

## callees

- `0x180035830`
- `0x180044a74`
- `0x180044d74`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044be6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044be6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180044bb7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180044bb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044bf0`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180044b9a`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180044b9a`

## pseudocode

```c
__int64 __fastcall CGlobalThumbsDBStore::_CanWrite(CGlobalThumbsDBStore *this, struct IShellItem2 *a2)
{
  struct IShellItem2Vtbl *lpVtbl; // rax
  struct IShellItem2Vtbl *v5; // rax
  unsigned int v6; // edi
  int v7; // ebx
  DWORD dwRevision[2]; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR pObjectName; // [rsp+50h] [rbp-20h] BYREF
  PACL ppDacl; // [rsp+58h] [rbp-18h] BYREF
  WORD pControl[2]; // [rsp+60h] [rbp-10h] BYREF
  int v14; // [rsp+64h] [rbp-Ch] BYREF

  lpVtbl = a2->lpVtbl;
  v14 = 0;
  if ( ((unsigned int (__fastcall *)(struct IShellItem2 *, __int64, int *))lpVtbl->GetAttributes)(a2, 0x2000, &v14)
    || (v5 = a2->lpVtbl,
        v6 = 0,
        *(_QWORD *)dwRevision = 0,
        ((int (__fastcall *)(struct IShellItem2 *, DWORD *))v5->GetParent)(a2, dwRevision) >= 0)
    && (*(_DWORD *)pControl = 0,
        v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, WORD *))(**(_QWORD **)dwRevision + 48LL))(
               *(_QWORD *)dwRevision,
               0x2000,
               pControl),
        LOBYTE(v6) = v7 == 0,
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)dwRevision + 16LL))(*(_QWORD *)dwRevision),
        !v7) )
  {
    if ( (unsigned int)CGlobalThumbsDBStore::_IsItemFromReadOnlyShare(this, a2) )
    {
      return 0;
    }
    else
    {
      pObjectName = 0;
      v6 = 1;
      if ( ((int (__fastcall *)(struct IShellItem2 *, __int64, LPCWSTR *))a2->lpVtbl->GetDisplayName)(
             a2,
             2147844096LL,
             &pObjectName) >= 0 )
      {
        v6 = 0;
        ppDacl = 0;
        pSecurityDescriptor = 0;
        if ( !GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &pSecurityDescriptor) )
        {
          pControl[0] = 0;
          dwRevision[0] = 0;
          if ( GetSecurityDescriptorControl(pSecurityDescriptor, pControl, dwRevision)
            && (pControl[0] & 0x1000) == 0
            && (!ppDacl || ppDacl[1].AclRevision != 1 || (ppDacl[1].Sbz1 & 0x10) != 0) )
          {
            v6 = 1;
          }
          LocalFree(pSecurityDescriptor);
        }
        CoTaskMemFree((LPVOID)pObjectName);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180044a74  mov     [rsp-18h+arg_10], rbx
0x180044a79  mov     [rsp-18h+arg_18], rsi
0x180044a7e  push    rbp
0x180044a7f  push    rdi
0x180044a80  push    r14
0x180044a82  mov     rbp, rsp
0x180044a85  sub     rsp, 70h
0x180044a89  mov     rax, cs:__security_cookie
0x180044a90  xor     rax, rsp
0x180044a93  mov     [rbp+var_8], rax
0x180044a97  mov     rax, [rdx]
0x180044a9a  lea     r8, [rbp+var_C]
0x180044a9e  mov     rsi, rdx
0x180044aa1  mov     [rbp+var_C], 0
0x180044aa8  mov     r14, rcx
0x180044aab  mov     ebx, 2000h
0x180044ab0  mov     edx, ebx
0x180044ab2  mov     rcx, rsi
0x180044ab5  mov     rax, [rax+30h]
0x180044ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044abe  test    eax, eax
0x180044ac0  jnz     short loc_180044B1F
0x180044ac2  mov     rax, [rsi]
0x180044ac5  lea     rdx, [rbp+dwRevision]
0x180044ac9  xor     edi, edi
0x180044acb  mov     rcx, rsi
0x180044ace  mov     qword ptr [rbp+dwRevision], rdi
0x180044ad2  mov     rax, [rax+20h]
0x180044ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044adb  test    eax, eax
0x180044add  js      loc_180044BFA
0x180044ae3  mov     rcx, qword ptr [rbp+dwRevision]
0x180044ae7  lea     r8, [rbp+pControl]
0x180044aeb  mov     dword ptr [rbp+pControl], edi
0x180044aee  mov     edx, ebx
0x180044af0  mov     rax, [rcx]
0x180044af3  mov     rax, [rax+30h]
0x180044af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044afc  mov     rdx, qword ptr [rbp+dwRevision]
0x180044b00  test    eax, eax
0x180044b02  mov     ebx, eax
0x180044b04  setz    dil
0x180044b08  mov     rcx, [rdx]
0x180044b0b  mov     rax, [rcx+10h]
0x180044b0f  mov     rcx, rdx
0x180044b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b17  test    ebx, ebx
0x180044b19  jnz     loc_180044BFA
0x180044b1f  mov     rdx, rsi; struct IShellItem2 *
0x180044b22  mov     rcx, r14; this
0x180044b25  call    ?_IsItemFromReadOnlyShare@CGlobalThumbsDBStore@@AEAAHPEAUIShellItem2@@@Z; CGlobalThumbsDBStore::_IsItemFromReadOnlyShare(IShellItem2 *)
0x180044b2a  test    eax, eax
0x180044b2c  jnz     loc_180044BF8
0x180044b32  lea     ebx, [rax+1]
0x180044b35  mov     [rbp+pObjectName], 0
0x180044b3d  mov     rax, [rsi]
0x180044b40  lea     r8, [rbp+pObjectName]
0x180044b44  mov     edx, 80058000h
0x180044b49  mov     rcx, rsi
0x180044b4c  mov     edi, ebx
0x180044b4e  mov     rax, [rax+28h]
0x180044b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b57  test    eax, eax
0x180044b59  js      loc_180044BFA
0x180044b5f  mov     rcx, [rbp+pObjectName]; pObjectName
0x180044b63  lea     rax, [rbp+pSecurityDescriptor]
0x180044b67  mov     [rsp+70h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180044b6c  lea     r8d, [rbx+3]; SecurityInfo
0x180044b70  xor     edi, edi
0x180044b72  mov     [rbp+var_18], 0
0x180044b7a  lea     rax, [rbp+var_18]
0x180044b7e  mov     [rsp+70h+ppSacl], rdi; ppSacl
0x180044b83  mov     [rsp+70h+ppDacl], rax; ppDacl
0x180044b88  xor     r9d, r9d; ppsidOwner
0x180044b8b  mov     edx, ebx; ObjectType
0x180044b8d  mov     [rsp+70h+ppsidGroup], rdi; ppsidGroup
0x180044b92  mov     [rbp+pSecurityDescriptor], 0
0x180044b9a  call    cs:__imp_GetNamedSecurityInfoW
0x180044ba0  test    eax, eax
0x180044ba2  jnz     short loc_180044BEC
0x180044ba4  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180044ba8  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180044bac  lea     rdx, [rbp+pControl]; pControl
0x180044bb0  mov     [rbp+pControl], ax
0x180044bb4  mov     [rbp+dwRevision], eax
0x180044bb7  call    cs:__imp_GetSecurityDescriptorControl
0x180044bbd  test    eax, eax
0x180044bbf  jz      short loc_180044BE2
0x180044bc1  mov     eax, 1000h
0x180044bc6  test    [rbp+pControl], ax
0x180044bca  jnz     short loc_180044BE2
0x180044bcc  mov     rax, [rbp+var_18]
0x180044bd0  test    rax, rax
0x180044bd3  jz      short loc_180044BE0
0x180044bd5  cmp     [rax+8], bl
0x180044bd8  jnz     short loc_180044BE0
0x180044bda  test    byte ptr [rax+9], 10h
0x180044bde  jz      short loc_180044BE2
0x180044be0  mov     edi, ebx
0x180044be2  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x180044be6  call    cs:__imp_LocalFree
0x180044bec  mov     rcx, [rbp+pObjectName]; pv
0x180044bf0  call    cs:__imp_CoTaskMemFree
0x180044bf6  jmp     short loc_180044BFA
0x180044bf8  xor     edi, edi
0x180044bfa  mov     eax, edi
0x180044bfc  mov     rcx, [rbp+var_8]
0x180044c00  xor     rcx, rsp; StackCookie
0x180044c03  call    __security_check_cookie
0x180044c08  lea     r11, [rsp+70h+var_s0]
0x180044c0d  mov     rbx, [r11+30h]
0x180044c11  mov     rsi, [r11+38h]
0x180044c15  mov     rsp, r11
0x180044c18  pop     r14
0x180044c1a  pop     rdi
0x180044c1b  pop     rbp
0x180044c1c  retn
```
