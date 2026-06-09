# CreateInstance

- ea: `0x180014410`
- end: `0x1800144b9`
- name: `CreateInstance`
- size: `169`
- prototype: `__int64 __fastcall(void *Buf2, struct IUnknown *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800141c0`
- `0x180014410`
- `0x1800158f9`

## pseudocode

```c
__int64 __fastcall CreateInstance(void *Buf2, struct IUnknown *a2, struct _GUID *a3, void **a4)
{
  __int64 result; // rax
  int v9; // ebx
  _QWORD v10[2]; // [rsp+20h] [rbp-58h] BYREF
  int v11; // [rsp+30h] [rbp-48h]

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v9 = 0;
  while ( memcmp_0(*(&g_ComClassTemplates + 2 * v9), Buf2, 0x10u) )
  {
    if ( ++v9 >= 1 )
      return 2147746065LL;
  }
  _InterlockedIncrement(&g_cActiveObjects);
  v10[1] = &g_ComClassTemplates + 2 * v9;
  v10[0] = &CClassFactory::`vftable';
  v11 = 0;
  result = CClassFactory::CreateInstance((CClassFactory *)v10, a2, a3, a4);
  _InterlockedDecrement(&g_cActiveObjects);
  return result;
}

```

## disassembly

```asm
0x180014410  push    rbx
0x180014412  push    rbp
0x180014413  push    rsi
0x180014414  push    rdi
0x180014415  push    r14
0x180014417  push    r15
0x180014419  sub     rsp, 48h
0x18001441d  mov     rdi, r9
0x180014420  mov     rbp, r8
0x180014423  mov     r14, rdx
0x180014426  mov     r15, rcx
0x180014429  test    r9, r9
0x18001442c  jnz     short loc_180014435
0x18001442e  mov     eax, 80004003h
0x180014433  jmp     short loc_1800144AC
0x180014435  mov     qword ptr [r9], 0
0x18001443c  xor     ebx, ebx
0x18001443e  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x180014445  movsxd  rsi, ebx
0x180014448  shl     rsi, 4
0x18001444c  mov     r8d, 10h; Size
0x180014452  add     rsi, rcx
0x180014455  mov     rdx, r15; Buf2
0x180014458  mov     rcx, [rsi]; Buf1
0x18001445b  call    memcmp_0
0x180014460  test    eax, eax
0x180014462  jz      short loc_180014472
0x180014464  inc     ebx
0x180014466  cmp     ebx, 1
0x180014469  jl      short loc_18001443E
0x18001446b  mov     eax, 80040111h
0x180014470  jmp     short loc_1800144AC
0x180014472  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180014479  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180014480  mov     [rsp+78h+var_50], rsi
0x180014485  mov     r9, rdi; void **
0x180014488  mov     [rsp+78h+var_58], rax
0x18001448d  mov     r8, rbp; struct _GUID *
0x180014490  mov     [rsp+78h+var_48], 0
0x180014498  mov     rdx, r14; struct IUnknown *
0x18001449b  lea     rcx, [rsp+78h+var_58]; this
0x1800144a0  call    ?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
0x1800144a5  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800144ac  add     rsp, 48h
0x1800144b0  pop     r15
0x1800144b2  pop     r14
0x1800144b4  pop     rdi
0x1800144b5  pop     rsi
0x1800144b6  pop     rbp
0x1800144b7  pop     rbx
0x1800144b8  retn
```
