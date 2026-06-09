# CSecurityExtensionCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008f70`
- end: `0x180009073`
- name: `?CreateInstance@CSecurityExtensionCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `259`
- prototype: `__int64 __fastcall(CSecurityExtensionCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008f70`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008fb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008fb7`

## pseudocode

```c
__int64 __fastcall CSecurityExtensionCF::CreateInstance(
        CSecurityExtensionCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // edi
  _QWORD *v9; // rbx
  int v10; // eax

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  if ( *((_DWORD *)this + 3) != 3 )
  {
    v8 = -2147467262;
    if ( *((_DWORD *)this + 3) != 1 )
      return v8;
  }
  v9 = LocalAlloc(0x40u, 0x58u);
  if ( v9 )
  {
    v10 = *((_DWORD *)this + 3);
    *v9 = &CSecurityExtension::`vftable'{for `IShellExtInit'};
    v9[1] = &CSecurityExtension::`vftable'{for `IShellPropSheetExt'};
    v9[2] = &CSecurityExtension::`vftable'{for `IElevatedNtfsSecurity'};
    *((_DWORD *)v9 + 6) = 1;
    *((_DWORD *)v9 + 7) = v10;
    *((_DWORD *)v9 + 10) = -1;
    *((_DWORD *)v9 + 11) = 131091;
    v9[8] = 0;
    v9[9] = 0;
    *((_DWORD *)v9 + 20) = 0;
    v9[4] = 0;
    v9[6] = 0;
    v9[7] = 0;
    _InterlockedIncrement(&g_cRefThisDll);
    v8 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v9)(v9, a3, a4);
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    return v8;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180008f70  push    rbx
0x180008f72  push    rbp
0x180008f73  push    rsi
0x180008f74  push    rdi
0x180008f75  push    r14
0x180008f77  sub     rsp, 20h
0x180008f7b  mov     qword ptr [r9], 0
0x180008f82  mov     r14, r9
0x180008f85  mov     rbp, r8
0x180008f88  mov     rsi, rcx
0x180008f8b  test    rdx, rdx
0x180008f8e  jz      short loc_180008F9A
0x180008f90  mov     eax, 80040110h
0x180008f95  jmp     loc_180009068
0x180008f9a  cmp     dword ptr [rcx+0Ch], 3
0x180008f9e  jz      short loc_180008FAF
0x180008fa0  cmp     dword ptr [rcx+0Ch], 1
0x180008fa4  mov     edi, 80004002h
0x180008fa9  jnz     loc_18000905F
0x180008faf  mov     edx, 58h ; 'X'; uBytes
0x180008fb4  lea     ecx, [rdx-18h]; uFlags
0x180008fb7  call    cs:__imp_LocalAlloc
0x180008fbd  mov     rbx, rax
0x180008fc0  test    rax, rax
0x180008fc3  jz      loc_180009063
0x180008fc9  mov     eax, [rsi+0Ch]
0x180008fcc  lea     rcx, ??_7CSecurityExtension@@6BIShellExtInit@@@; const CSecurityExtension::`vftable'{for `IShellExtInit'}
0x180008fd3  mov     [rbx], rcx
0x180008fd6  lea     rcx, ??_7CSecurityExtension@@6BIShellPropSheetExt@@@; const CSecurityExtension::`vftable'{for `IShellPropSheetExt'}
0x180008fdd  mov     [rbx+8], rcx
0x180008fe1  lea     rcx, ??_7CSecurityExtension@@6BIElevatedNtfsSecurity@@@; const CSecurityExtension::`vftable'{for `IElevatedNtfsSecurity'}
0x180008fe8  mov     [rbx+10h], rcx
0x180008fec  mov     dword ptr [rbx+18h], 1
0x180008ff3  mov     [rbx+1Ch], eax
0x180008ff6  mov     dword ptr [rbx+28h], 0FFFFFFFFh
0x180008ffd  mov     dword ptr [rbx+2Ch], 20013h
0x180009004  mov     qword ptr [rbx+40h], 0
0x18000900c  mov     qword ptr [rbx+48h], 0
0x180009014  mov     dword ptr [rbx+50h], 0
0x18000901b  mov     qword ptr [rbx+20h], 0
0x180009023  mov     qword ptr [rbx+30h], 0
0x18000902b  mov     qword ptr [rbx+38h], 0
0x180009033  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000903a  mov     rax, [rbx]
0x18000903d  mov     r8, r14
0x180009040  mov     rdx, rbp
0x180009043  mov     rcx, rbx
0x180009046  mov     rax, [rax]
0x180009049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000904e  mov     rcx, [rbx]
0x180009051  mov     edi, eax
0x180009053  mov     rax, [rcx+10h]
0x180009057  mov     rcx, rbx
0x18000905a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000905f  mov     eax, edi
0x180009061  jmp     short loc_180009068
0x180009063  mov     eax, 8007000Eh
0x180009068  add     rsp, 20h
0x18000906c  pop     r14
0x18000906e  pop     rdi
0x18000906f  pop     rsi
0x180009070  pop     rbp
0x180009071  pop     rbx
0x180009072  retn
```
