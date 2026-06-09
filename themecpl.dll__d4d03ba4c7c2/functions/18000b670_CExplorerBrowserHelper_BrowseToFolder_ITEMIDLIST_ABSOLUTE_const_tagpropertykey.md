# CExplorerBrowserHelper::BrowseToFolder(_ITEMIDLIST_ABSOLUTE const *,_tagpropertykey)

- ea: `0x18000b670`
- end: `0x18000b78c`
- name: `?BrowseToFolder@CExplorerBrowserHelper@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@U_tagpropertykey@@@Z`
- size: `284`
- prototype: `int(CExplorerBrowserHelper *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, struct _tagpropertykey *__struct_ptr)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000b670`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18000b721`
- `SHELL32!__imp_ILClone` at `0x18000b721`
- `SHLWAPI!__imp_IUnknown_Exec` at `0x18000b70e`
- `SHLWAPI!__imp_IUnknown_Exec` at `0x18000b70e`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000b6b3`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000b6b3`

## pseudocode

```c
__int64 __fastcall CExplorerBrowserHelper::BrowseToFolder(
        CExplorerBrowserHelper *this,
        const ITEMIDLIST *a2,
        struct _tagpropertykey *a3)
{
  GUID fmtid; // xmm0
  DWORD pid; // eax
  HRESULT v7; // edi
  __int64 v8; // rcx
  void *v10; // [rsp+40h] [rbp+8h] BYREF

  fmtid = a3->fmtid;
  pid = a3->pid;
  v10 = 0;
  *(GUID *)((char *)this + 100) = fmtid;
  *((_DWORD *)this + 29) = pid;
  v7 = IUnknown_QueryService(
         *((IUnknown **)this + 8),
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_000214e2_0000_0000_c000_000000000046,
         &v10);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v10 + 72LL))(v10, 0);
    if ( v7 >= 0 )
    {
      v8 = *((_QWORD *)this + 16);
      if ( v8 )
      {
        if ( (int)IUnknown_Exec(v8, 0, 23, 2, 0, 0) >= 0 )
        {
          *((_QWORD *)this + 17) = ILClone(a2);
          *((_BYTE *)this + 124) = 1;
        }
      }
      else
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, const ITEMIDLIST *, _QWORD))(**((_QWORD **)this + 9) + 104LL))(
               *((_QWORD *)this + 9),
               a2,
               0);
      }
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v10 + 72LL))(v10, 1);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b670  mov     r11, rsp
0x18000b673  mov     [r11+10h], rbx
0x18000b677  mov     [r11+18h], rsi
0x18000b67b  push    rdi
0x18000b67c  sub     rsp, 30h
0x18000b680  movups  xmm0, xmmword ptr [r8]
0x18000b684  mov     eax, [r8+10h]
0x18000b688  lea     r9, [r11+8]; ppvOut
0x18000b68c  mov     rsi, rdx
0x18000b68f  mov     qword ptr [r11+8], 0
0x18000b697  movups  xmmword ptr [rcx+64h], xmm0
0x18000b69b  mov     [rcx+74h], eax
0x18000b69e  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18000b6a5  mov     rbx, rcx
0x18000b6a8  lea     rdx, SID_STopLevelBrowser; guidService
0x18000b6af  mov     rcx, [rcx+40h]; punk
0x18000b6b3  call    cs:__imp_IUnknown_QueryService
0x18000b6ba  nop     dword ptr [rax+rax+00h]
0x18000b6bf  mov     edi, eax
0x18000b6c1  test    eax, eax
0x18000b6c3  js      loc_18000B779
0x18000b6c9  mov     rcx, [rsp+38h+arg_0]
0x18000b6ce  xor     edx, edx
0x18000b6d0  mov     rax, [rcx]
0x18000b6d3  mov     rax, [rax+48h]
0x18000b6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6dc  mov     edi, eax
0x18000b6de  test    eax, eax
0x18000b6e0  js      loc_18000B768
0x18000b6e6  mov     rcx, [rbx+80h]
0x18000b6ed  test    rcx, rcx
0x18000b6f0  jz      short loc_18000B73A
0x18000b6f2  xor     edx, edx
0x18000b6f4  mov     [rsp+38h+var_10], 0
0x18000b6fd  mov     [rsp+38h+var_18], 0
0x18000b706  lea     r9d, [rdx+2]
0x18000b70a  lea     r8d, [rdx+17h]
0x18000b70e  call    cs:__imp_IUnknown_Exec
0x18000b715  nop     dword ptr [rax+rax+00h]
0x18000b71a  test    eax, eax
0x18000b71c  js      short loc_18000B752
0x18000b71e  mov     rcx, rsi; pidl
0x18000b721  call    cs:__imp_ILClone
0x18000b728  nop     dword ptr [rax+rax+00h]
0x18000b72d  mov     [rbx+88h], rax
0x18000b734  mov     byte ptr [rbx+7Ch], 1
0x18000b738  jmp     short loc_18000B752
0x18000b73a  mov     rcx, [rbx+48h]
0x18000b73e  xor     r8d, r8d
0x18000b741  mov     rdx, rsi
0x18000b744  mov     rax, [rcx]
0x18000b747  mov     rax, [rax+68h]
0x18000b74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b750  mov     edi, eax
0x18000b752  mov     rcx, [rsp+38h+arg_0]
0x18000b757  mov     edx, 1
0x18000b75c  mov     rax, [rcx]
0x18000b75f  mov     rax, [rax+48h]
0x18000b763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b768  mov     rcx, [rsp+38h+arg_0]
0x18000b76d  mov     rax, [rcx]
0x18000b770  mov     rax, [rax+10h]
0x18000b774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b779  mov     rbx, [rsp+38h+arg_8]
0x18000b77e  mov     eax, edi
0x18000b780  mov     rsi, [rsp+38h+arg_10]
0x18000b785  add     rsp, 30h
0x18000b789  pop     rdi
0x18000b78a  retn
```
