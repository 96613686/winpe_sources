# NdrpDisableAllocate

- ea: `0x1800978bc`
- end: `0x180097983`
- name: `NdrpDisableAllocate`
- size: `199`
- prototype: `void __fastcall(int)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ee10`
- `0x180097880`
- `0x1800c76f0`
- `0x1800c7890`
- `0x1800d2ad0`

## callees

- `0x180023a40`
- `0x1800978bc`
- `0x1800a6cd8`
- `0x1800c7440`
- `0x1800c7508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800978ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009794b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800978ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009794b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800978e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800978e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009795e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009795e`

## pseudocode

```c
void __fastcall NdrpDisableAllocate(int a1)
{
  struct _ALLOCATION_CONTEXT *AllocContext; // rax
  struct _ALLOCATION_CONTEXT *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int v5; // edx
  int v6; // esi

  AllocContext = GetAllocContext();
  v3 = AllocContext;
  if ( AllocContext )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)AllocContext + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)AllocContext + 24));
    if ( a1 )
    {
      if ( !*((_QWORD *)v3 + 9) )
      {
        LeaveCriticalSection(v4);
        return;
      }
      v5 = *(_DWORD *)(*((_QWORD *)v3 + 10) + 4LL * (unsigned int)--*((_DWORD *)v3 + 23));
    }
    else
    {
      v5 = *((_DWORD *)v3 + 4) - 1;
    }
    v6 = 0;
    if ( *((_DWORD *)v3 + 4) )
    {
      *((_DWORD *)v3 + 4) = v5;
      if ( v5 )
      {
LABEL_12:
        LeaveCriticalSection(v4);
        if ( v6 )
        {
          DeleteCriticalSection(v4);
          FreeWrapper(v3);
        }
        return;
      }
      NdrpReleaseMemory(v3);
    }
    if ( !*((_DWORD *)v3 + 16) )
    {
      v6 = 1;
      SetAllocContext(0);
    }
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x1800978bc  mov     [rsp+arg_0], rbx
0x1800978c1  mov     [rsp+arg_8], rsi
0x1800978c6  push    rdi
0x1800978c7  sub     rsp, 20h
0x1800978cb  mov     esi, ecx
0x1800978cd  call    ?GetAllocContext@@YAPEAU_ALLOCATION_CONTEXT@@XZ; GetAllocContext(void)
0x1800978d2  mov     rbx, rax
0x1800978d5  test    rax, rax
0x1800978d8  jz      loc_180097972
0x1800978de  lea     rdi, [rax+18h]
0x1800978e2  mov     rcx, rdi; lpCriticalSection
0x1800978e5  call    cs:__imp_EnterCriticalSection
0x1800978ec  nop     dword ptr [rax+rax+00h]
0x1800978f1  test    esi, esi
0x1800978f3  jz      short loc_18009791C
0x1800978f5  cmp     qword ptr [rbx+48h], 0
0x1800978fa  jnz     short loc_18009790D
0x1800978fc  mov     rcx, rdi; lpCriticalSection
0x1800978ff  call    cs:__imp_LeaveCriticalSection
0x180097906  nop     dword ptr [rax+rax+00h]
0x18009790b  jmp     short loc_180097972
0x18009790d  dec     dword ptr [rbx+5Ch]
0x180097910  mov     ecx, [rbx+5Ch]
0x180097913  mov     rax, [rbx+50h]
0x180097917  mov     edx, [rax+rcx*4]
0x18009791a  jmp     short loc_180097921
0x18009791c  mov     edx, [rbx+10h]
0x18009791f  dec     edx
0x180097921  xor     esi, esi
0x180097923  cmp     [rbx+10h], esi
0x180097926  jz      short loc_180097937
0x180097928  mov     [rbx+10h], edx
0x18009792b  test    edx, edx
0x18009792d  jnz     short loc_180097948
0x18009792f  mov     rcx, rbx
0x180097932  call    NdrpReleaseMemory
0x180097937  cmp     [rbx+40h], esi
0x18009793a  jnz     short loc_180097948
0x18009793c  xor     ecx, ecx; lpTlsValue
0x18009793e  mov     esi, 1
0x180097943  call    ?SetAllocContext@@YAXPEAU_ALLOCATION_CONTEXT@@@Z; SetAllocContext(_ALLOCATION_CONTEXT *)
0x180097948  mov     rcx, rdi; lpCriticalSection
0x18009794b  call    cs:__imp_LeaveCriticalSection
0x180097952  nop     dword ptr [rax+rax+00h]
0x180097957  test    esi, esi
0x180097959  jz      short loc_180097972
0x18009795b  mov     rcx, rdi; lpCriticalSection
0x18009795e  call    cs:__imp_DeleteCriticalSection
0x180097965  nop     dword ptr [rax+rax+00h]
0x18009796a  mov     rcx, rbx; lpMem
0x18009796d  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180097972  mov     rbx, [rsp+28h+arg_0]
0x180097977  mov     rsi, [rsp+28h+arg_8]
0x18009797c  add     rsp, 20h
0x180097980  pop     rdi
0x180097981  retn
```
