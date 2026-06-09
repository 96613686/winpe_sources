# CNtSecurityDescriptor::GetDacl(void)

- ea: `0x18001c790`
- end: `0x18001c8f0`
- name: `?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ`
- size: `352`
- prototype: `struct CNtAcl *__fastcall(CNtSecurityDescriptor *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b730`
- `0x18003b580`

## callees

- `0x18000a290`
- `0x18001c790`
- `0x18001c990`
- `0x18001d19c`
- `0x18001d204`
- `0x18002ee96`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c893`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c893`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c8ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c8ab`

## string_xrefs

- `0x18001c89d`: `GetSecurityDescriptorDacl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CNtAcl *__fastcall CNtSecurityDescriptor::GetDacl(CNtSecurityDescriptor *this)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  CNtAcl *v3; // rax
  unsigned int v4; // edx
  CNtAcl *v5; // rbx
  struct _ACL *v6; // rdi
  void *v8; // rax
  DWORD SecurityDll; // eax
  int v10; // [rsp+50h] [rbp+8h] BYREF
  int v11; // [rsp+58h] [rbp+10h] BYREF
  void *Src; // [rsp+60h] [rbp+18h] BYREF
  CNtAcl *v13; // [rsp+68h] [rbp+20h]

  v10 = 0;
  v11 = 0;
  if ( *((_DWORD *)this + 2) )
    return 0;
  Src = 0;
  v1 = *(_QWORD *)this;
  ProcAddress = (FARPROC)qword_1800702C0;
  if ( !qword_1800702C0 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
    }
    else
    {
      ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorDacl");
      qword_1800702C0 = (__int64)ProcAddress;
      if ( ProcAddress )
        goto LABEL_3;
    }
    return 0;
  }
LABEL_3:
  if ( !((unsigned int (__fastcall *)(__int64, int *, void **, int *))ProcAddress)(v1, &v10, &Src, &v11) || !v10 )
    return 0;
  v3 = (CNtAcl *)CWin32DefaultArena::WbemMemAlloc(0x10u);
  v5 = v3;
  v13 = v3;
  if ( v3 )
  {
    v6 = (struct _ACL *)Src;
    *(_QWORD *)v3 = 0;
    *((_DWORD *)v3 + 2) = 0;
    if ( v6 )
    {
      if ( (unsigned int)DLIsValidAcl(v6) )
      {
        v8 = CWin32DefaultArena::WbemMemAlloc(v6->AclSize);
        *(_QWORD *)v5 = v8;
        if ( v8 )
        {
          memset_0(v8, 0, v6->AclSize);
          memcpy_0(*(void **)v5, v6, v6->AclSize);
        }
        else
        {
          *((_DWORD *)v5 + 2) = 1;
        }
      }
      else
      {
        *((_DWORD *)v5 + 2) = 3;
      }
    }
    else
    {
      *((_DWORD *)v3 + 2) = 2;
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v5 )
  {
    if ( *((_DWORD *)v5 + 2) )
    {
      CNtAcl::`scalar deleting destructor'(v5, v4);
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001c790  push    rbx
0x18001c792  push    rdi
0x18001c793  sub     rsp, 38h
0x18001c797  mov     [rsp+48h+arg_0], 0
0x18001c79f  mov     [rsp+48h+arg_8], 0
0x18001c7a7  cmp     dword ptr [rcx+8], 0
0x18001c7ab  jnz     loc_18001C899
0x18001c7b1  mov     [rsp+48h+Src], 0
0x18001c7ba  mov     rbx, [rcx]
0x18001c7bd  mov     rax, cs:qword_1800702C0
0x18001c7c4  test    rax, rax
0x18001c7c7  jz      loc_18001C888
0x18001c7cd  lea     r9, [rsp+48h+arg_8]
0x18001c7d2  lea     r8, [rsp+48h+Src]
0x18001c7d7  lea     rdx, [rsp+48h+arg_0]
0x18001c7dc  mov     rcx, rbx
0x18001c7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7e4  test    eax, eax
0x18001c7e6  jz      loc_18001C899
0x18001c7ec  cmp     [rsp+48h+arg_0], 0
0x18001c7f1  jz      loc_18001C899
0x18001c7f7  mov     ecx, 10h; unsigned __int64
0x18001c7fc  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001c801  mov     rbx, rax
0x18001c804  mov     [rsp+48h+arg_18], rax
0x18001c809  test    rax, rax
0x18001c80c  jz      loc_18001C8DA
0x18001c812  mov     rdi, [rsp+48h+Src]
0x18001c817  mov     qword ptr [rax], 0
0x18001c81e  mov     dword ptr [rax+8], 0
0x18001c825  test    rdi, rdi
0x18001c828  jnz     short loc_18001C84A
0x18001c82a  mov     dword ptr [rax+8], 2
0x18001c831  test    rbx, rbx
0x18001c834  jz      short loc_18001C840
0x18001c836  cmp     dword ptr [rbx+8], 0
0x18001c83a  jnz     loc_18001C8E1
0x18001c840  mov     rax, rbx
0x18001c843  add     rsp, 38h
0x18001c847  pop     rdi
0x18001c848  pop     rbx
0x18001c849  retn
0x18001c84a  mov     rcx, rdi; struct _ACL *
0x18001c84d  call    ?DLIsValidAcl@@YAHPEAU_ACL@@@Z; DLIsValidAcl(_ACL *)
0x18001c852  test    eax, eax
0x18001c854  jz      short loc_18001C8C2
0x18001c856  movzx   ecx, word ptr [rdi+2]; unsigned __int64
0x18001c85a  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001c85f  mov     [rbx], rax
0x18001c862  test    rax, rax
0x18001c865  jz      short loc_18001C8CE
0x18001c867  movzx   r8d, word ptr [rdi+2]; Size
0x18001c86c  xor     edx, edx; Val
0x18001c86e  mov     rcx, rax; void *
0x18001c871  call    memset_0
0x18001c876  movzx   r8d, word ptr [rdi+2]; Size
0x18001c87b  mov     rdx, rdi; Src
0x18001c87e  mov     rcx, [rbx]; void *
0x18001c881  call    memcpy_0
0x18001c886  jmp     short loc_18001C831
0x18001c888  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001c88d  test    eax, eax
0x18001c88f  jz      short loc_18001C89D
0x18001c891  mov     ecx, eax; dwErrCode
0x18001c893  call    cs:__imp_SetLastError
0x18001c899  xor     eax, eax
0x18001c89b  jmp     short loc_18001C843
0x18001c89d  lea     rdx, aGetsecuritydes_0; "GetSecurityDescriptorDacl"
0x18001c8a4  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001c8ab  call    cs:__imp_GetProcAddress
0x18001c8b1  mov     cs:qword_1800702C0, rax
0x18001c8b8  test    rax, rax
0x18001c8bb  jz      short loc_18001C899
0x18001c8bd  jmp     loc_18001C7CD
0x18001c8c2  mov     dword ptr [rbx+8], 3
0x18001c8c9  jmp     loc_18001C831
0x18001c8ce  mov     dword ptr [rbx+8], 1
0x18001c8d5  jmp     loc_18001C831
0x18001c8da  xor     ebx, ebx
0x18001c8dc  jmp     loc_18001C831
0x18001c8e1  mov     rcx, rbx; this
0x18001c8e4  call    ??_GCNtAcl@@QEAAPEAXI@Z; CNtAcl::`scalar deleting destructor'(uint)
0x18001c8e9  xor     ebx, ebx
0x18001c8eb  jmp     loc_18001C840
```
