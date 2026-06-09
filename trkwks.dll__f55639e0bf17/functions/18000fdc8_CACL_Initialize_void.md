# CACL::Initialize(void)

- ea: `0x18000fdc8`
- end: `0x18000fe25`
- name: `?Initialize@CACL@@QEAAXXZ`
- size: `93`
- prototype: `void __fastcall(CACL *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d594`

## callees

- `0x18000d038`
- `0x18000dae8`
- `0x18000fdc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe0d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000fe03`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000fe03`

## pseudocode

```c
void __fastcall CACL::Initialize(CACL *this)
{
  struct _ACL *v2; // rax
  DWORD LastError; // eax

  *((_DWORD *)this + 3) |= 1u;
  v2 = (struct _ACL *)operator new(0x80u);
  *(_QWORD *)this = v2;
  if ( !v2 )
    TrkRaiseWin32Error(8);
  *((_DWORD *)this + 2) = 128;
  if ( !InitializeAcl(v2, 0x80u, 2u) )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  *((_DWORD *)this + 3) |= 2u;
}

```

## disassembly

```asm
0x18000fdc8  push    rbx
0x18000fdca  sub     rsp, 20h
0x18000fdce  or      dword ptr [rcx+0Ch], 1
0x18000fdd2  mov     rbx, rcx
0x18000fdd5  mov     ecx, 80h; Size
0x18000fdda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fddf  mov     [rbx], rax
0x18000fde2  test    rax, rax
0x18000fde5  jnz     short loc_18000FDF0
0x18000fde7  lea     ecx, [rax+8]; int
0x18000fdea  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000fdf0  mov     edx, 80h; nAclLength
0x18000fdf5  mov     dword ptr [rbx+8], 80h
0x18000fdfc  mov     rcx, rax; pAcl
0x18000fdff  lea     r8d, [rdx-7Eh]; dwAclRevision
0x18000fe03  call    cs:__imp_InitializeAcl
0x18000fe09  test    eax, eax
0x18000fe0b  jnz     short loc_18000FE1B
0x18000fe0d  call    cs:__imp_GetLastError
0x18000fe13  mov     ecx, eax; int
0x18000fe15  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000fe1b  or      dword ptr [rbx+0Ch], 2
0x18000fe1f  add     rsp, 20h
0x18000fe23  pop     rbx
0x18000fe24  retn
```
