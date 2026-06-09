# CAANapEnforcementClientCallback::~CAANapEnforcementClientCallback(void)

- ea: `0x180002c0c`
- end: `0x180002c8d`
- name: `??1CAANapEnforcementClientCallback@@QEAA@XZ`
- size: `129`
- prototype: `void __fastcall(CAANapEnforcementClientCallback *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b20`

## callees

- `0x180002b84`
- `0x180002c0c`
- `0x18000c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002c6c`
- `KERNEL32!DeleteCriticalSection` at `0x180002c6c`
- `KERNEL32!LocalFree` at `0x180002c75`
- `KERNEL32!LocalFree` at `0x180002c75`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAANapEnforcementClientCallback::~CAANapEnforcementClientCallback(
        CAANapEnforcementClientCallback *this)
{
  void *v2; // rdi

  *(_QWORD *)this = &CAANapEnforcementClientCallback::`vftable';
  if ( g_pNECBinding )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pNECBinding + 16LL))(g_pNECBinding);
    g_pNECBinding = 0;
  }
  std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::~_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>((char *)this + 40);
  if ( *((_DWORD *)this + 8) )
  {
    v2 = (void *)*((_QWORD *)this + 3);
    if ( v2 )
    {
      DeleteCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
      LocalFree(v2);
      *((_DWORD *)this + 8) = 0;
    }
  }
}

```

## disassembly

```asm
0x180002c0c  push    rdi
0x180002c0e  sub     rsp, 30h
0x180002c12  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002c1b  mov     [rsp+38h+arg_0], rbx
0x180002c20  mov     rbx, rcx
0x180002c23  lea     rax, ??_7CAANapEnforcementClientCallback@@6B@; const CAANapEnforcementClientCallback::`vftable'
0x180002c2a  mov     [rcx], rax
0x180002c2d  mov     rcx, cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA; INapEnforcementClientBinding * g_pNECBinding
0x180002c34  test    rcx, rcx
0x180002c37  jz      short loc_180002C50
0x180002c39  mov     rax, [rcx]
0x180002c3c  mov     rax, [rax+10h]
0x180002c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c45  mov     cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA, 0; INapEnforcementClientBinding * g_pNECBinding
0x180002c50  lea     rcx, [rbx+28h]
0x180002c54  call    ??1?$_Tree@V?$_Tmap_traits@PEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@U?$less@PEAVCAANapConnection@@@std@@V?$allocator@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::~_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>(void)
0x180002c59  nop
0x180002c5a  cmp     dword ptr [rbx+20h], 0
0x180002c5e  jz      short loc_180002C82
0x180002c60  mov     rdi, [rbx+18h]
0x180002c64  test    rdi, rdi
0x180002c67  jz      short loc_180002C82
0x180002c69  mov     rcx, rdi; lpCriticalSection
0x180002c6c  call    cs:__imp_DeleteCriticalSection
0x180002c72  mov     rcx, rdi; hMem
0x180002c75  call    cs:__imp_LocalFree
0x180002c7b  mov     dword ptr [rbx+20h], 0
0x180002c82  mov     rbx, [rsp+38h+arg_0]
0x180002c87  add     rsp, 30h
0x180002c8b  pop     rdi
0x180002c8c  retn
```
