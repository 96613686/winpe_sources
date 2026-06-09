# CElevatedFactoryServerManager::_GetExistingFactory(_GUID const &,IElevatedFactoryServer * *)

- ea: `0x1800023cc`
- end: `0x180002459`
- name: `?_GetExistingFactory@CElevatedFactoryServerManager@@IEAAXAEBU_GUID@@PEAPEAUIElevatedFactoryServer@@@Z`
- size: `141`
- prototype: `void __fastcall(CElevatedFactoryServerManager *__hidden this, const struct _GUID *, struct IElevatedFactoryServer **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001d00`
- `0x180001f80`

## callees

- `0x1800023cc`
- `0x180003460`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002452`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023ec`

## pseudocode

```c
void __fastcall CElevatedFactoryServerManager::_GetExistingFactory(
        CElevatedFactoryServerManager *this,
        const struct _GUID *a2,
        struct IElevatedFactoryServer **a3)
{
  int i; // ebx
  struct _DPA *v7; // rcx
  int v8; // eax
  _QWORD *Ptr; // rax
  struct IElevatedFactoryServer *v10; // rcx

  *a3 = 0;
  EnterCriticalSection(&g_csDll);
  for ( i = 0; !*a3; ++i )
  {
    v7 = (struct _DPA *)*((_QWORD *)this + 1);
    if ( v7 )
      v8 = *(_DWORD *)v7;
    else
      v8 = 0;
    if ( i >= v8 )
      break;
    Ptr = g_pfn_DPA_GetPtr(v7, i);
    if ( Ptr[1] == *(_QWORD *)&a2->Data1 && Ptr[2] == *(_QWORD *)a2->Data4 )
    {
      v10 = (struct IElevatedFactoryServer *)Ptr[3];
      *a3 = v10;
      (*(void (__fastcall **)(struct IElevatedFactoryServer *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  LeaveCriticalSection(&g_csDll);
}

```

## disassembly

```asm
0x1800023cc  push    rbx
0x1800023ce  push    rbp
0x1800023cf  push    rsi
0x1800023d0  push    rdi
0x1800023d1  sub     rsp, 28h
0x1800023d5  mov     rbp, rcx
0x1800023d8  mov     qword ptr [r8], 0
0x1800023df  lea     rcx, g_csDll; lpCriticalSection
0x1800023e6  mov     rdi, r8
0x1800023e9  mov     rsi, rdx
0x1800023ec  call    cs:__imp_EnterCriticalSection
0x1800023f2  xor     ebx, ebx
0x1800023f4  cmp     [rdi], rbx
0x1800023f7  jnz     short loc_180002443
0x1800023f9  mov     rcx, [rbp+8]; hdpa
0x1800023fd  test    rcx, rcx
0x180002400  jz      short loc_180002406
0x180002402  mov     eax, [rcx]
0x180002404  jmp     short loc_180002408
0x180002406  xor     eax, eax
0x180002408  cmp     ebx, eax
0x18000240a  jge     short loc_180002443
0x18000240c  movsxd  rdx, ebx; i
0x18000240f  call    cs:g_pfn_DPA_GetPtr
0x180002415  mov     rcx, [rax+8]
0x180002419  cmp     rcx, [rsi]
0x18000241c  jnz     short loc_18000243B
0x18000241e  mov     rcx, [rax+10h]
0x180002422  cmp     rcx, [rsi+8]
0x180002426  jnz     short loc_18000243B
0x180002428  mov     rcx, [rax+18h]
0x18000242c  mov     [rdi], rcx
0x18000242f  mov     rax, [rcx]
0x180002432  mov     rax, [rax+8]
0x180002436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000243b  inc     ebx
0x18000243d  cmp     qword ptr [rdi], 0
0x180002441  jz      short loc_1800023F9
0x180002443  lea     rcx, g_csDll
0x18000244a  add     rsp, 28h
0x18000244e  pop     rdi
0x18000244f  pop     rsi
0x180002450  pop     rbp
0x180002451  pop     rbx
0x180002452  jmp     cs:__imp_LeaveCriticalSection
```
