# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800128ac`
- end: `0x18001296f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180010774`
- `0x180012d80`

## callees

- `0x1800128ac`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180012910`
- `KERNEL32!HeapAlloc` at `0x180012910`
- `KERNEL32!GetProcessHeap` at `0x1800128d7`
- `KERNEL32!GetProcessHeap` at `0x180012901`
- `KERNEL32!GetProcessHeap` at `0x18001293b`
- `KERNEL32!GetProcessHeap` at `0x1800128d7`
- `KERNEL32!GetProcessHeap` at `0x180012901`
- `KERNEL32!GetProcessHeap` at `0x18001293b`
- `KERNEL32!HeapFree` at `0x1800128e5`
- `KERNEL32!HeapFree` at `0x180012949`
- `KERNEL32!HeapFree` at `0x1800128e5`
- `KERNEL32!HeapFree` at `0x180012949`

## pseudocode

```c
__int64 __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    result = (__int64)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = (volatile signed __int32 *)result;
    if ( result )
    {
      *(_DWORD *)result = 0;
      if ( *this )
      {
        if ( _InterlockedExchangeAdd(*this, 0xFFFFFFFF) == 1 )
        {
          v10 = *this;
          v11 = GetProcessHeap();
          HeapFree(v11, 0, (LPVOID)v10);
        }
        this[1] = 0;
      }
      *this = v9;
      result = 1;
      this[1] = a2;
      _InterlockedAdd(v9, 1u);
    }
  }
  else
  {
    v4 = *this;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
      {
        v5 = *this;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, (LPVOID)v5);
      }
      *this = 0;
      this[1] = 0;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800128ac  push    rbx
0x1800128ae  push    rbp
0x1800128af  push    rsi
0x1800128b0  push    rdi
0x1800128b1  sub     rsp, 28h
0x1800128b5  mov     rbp, rdx
0x1800128b8  mov     rdi, rcx
0x1800128bb  test    rdx, rdx
0x1800128be  jnz     short loc_180012901
0x1800128c0  mov     rcx, [rcx]
0x1800128c3  test    rcx, rcx
0x1800128c6  jz      short loc_1800128FA
0x1800128c8  or      eax, 0FFFFFFFFh
0x1800128cb  lock xadd [rcx], eax
0x1800128cf  cmp     eax, 1
0x1800128d2  jnz     short loc_1800128EB
0x1800128d4  mov     rbx, [rdi]
0x1800128d7  call    cs:__imp_GetProcessHeap
0x1800128dd  mov     r8, rbx; lpMem
0x1800128e0  xor     edx, edx; dwFlags
0x1800128e2  mov     rcx, rax; hHeap
0x1800128e5  call    cs:__imp_HeapFree
0x1800128eb  mov     qword ptr [rdi], 0
0x1800128f2  mov     qword ptr [rdi+8], 0
0x1800128fa  mov     eax, 1
0x1800128ff  jmp     short loc_180012966
0x180012901  call    cs:__imp_GetProcessHeap
0x180012907  lea     r8, [rbp+4]; dwBytes
0x18001290b  xor     edx, edx; dwFlags
0x18001290d  mov     rcx, rax; hHeap
0x180012910  call    cs:__imp_HeapAlloc
0x180012916  mov     rsi, rax
0x180012919  test    rax, rax
0x18001291c  jz      short loc_180012966
0x18001291e  mov     dword ptr [rax], 0
0x180012924  mov     rcx, [rdi]
0x180012927  test    rcx, rcx
0x18001292a  jz      short loc_180012957
0x18001292c  or      eax, 0FFFFFFFFh
0x18001292f  lock xadd [rcx], eax
0x180012933  cmp     eax, 1
0x180012936  jnz     short loc_18001294F
0x180012938  mov     rbx, [rdi]
0x18001293b  call    cs:__imp_GetProcessHeap
0x180012941  mov     r8, rbx; lpMem
0x180012944  xor     edx, edx; dwFlags
0x180012946  mov     rcx, rax; hHeap
0x180012949  call    cs:__imp_HeapFree
0x18001294f  mov     qword ptr [rdi+8], 0
0x180012957  mov     [rdi], rsi
0x18001295a  mov     eax, 1
0x18001295f  mov     [rdi+8], rbp
0x180012963  lock add [rsi], eax
0x180012966  add     rsp, 28h
0x18001296a  pop     rdi
0x18001296b  pop     rsi
0x18001296c  pop     rbp
0x18001296d  pop     rbx
0x18001296e  retn
```
