# ParseUncPathEx

- ea: `0x18000ed90`
- end: `0x18000efb4`
- name: `ParseUncPathEx`
- size: `548`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000efbc`

## callees

- `0x1800015cc`
- `0x1800015e3`
- `0x18000ed90`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000eebb`
- `ntdll!RtlAllocateHeap` at `0x18000eebb`
- `KERNEL32!GetProcessHeap` at `0x18000ef5e`
- `KERNEL32!GetProcessHeap` at `0x18000ef5e`
- `KERNEL32!HeapFree` at `0x18000ef72`
- `KERNEL32!HeapFree` at `0x18000ef72`

## pseudocode

```c
__int64 __fastcall ParseUncPathEx(wchar_t *String1, _DWORD *a2, _QWORD *a3)
{
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  wchar_t *v11; // rax
  unsigned int v12; // ebx
  _WORD *Heap; // rdi
  unsigned __int64 v14; // rbp
  wchar_t *v15; // rax
  unsigned __int64 v16; // r14
  _WORD *v17; // rcx
  char *v18; // rsi
  __int16 v19; // ax
  _WORD *v20; // rax
  HANDLE ProcessHeap; // rax

  if ( !String1 )
    return 2147942487LL;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( String1[v8] );
  if ( v8 < 2 || wcsnicmp_0(String1, L"\\\\", 2u) )
  {
    v12 = 0;
    if ( a2 )
      *a2 = 0;
    if ( a3 )
      *a3 = 0;
    return v12;
  }
  v9 = -1;
  do
    ++v9;
  while ( String1[v9] );
  v10 = v9 >= 8 && wcsnicmp_0(String1, L"\\\\?\\UNC\\", 8u) == 0;
  v11 = wcschr_0((wchar_t *)((char *)String1 + (v10 ? 16LL : 4LL)), 0x5Cu);
  if ( v11 )
  {
    Heap = 0;
    v14 = -1;
    do
      ++v14;
    while ( String1[v14] );
    v15 = wcschr_0(v11 + 1, 0x5Cu);
    if ( v15 )
      v14 = v15 - String1;
    if ( a3 )
    {
      v12 = -2147024882;
      do
        ++v7;
      while ( String1[v7] );
      if ( v14 > v7 )
      {
        v12 = -2147024809;
      }
      else
      {
        v16 = v14 + 1;
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (v14 + 1));
        if ( Heap )
        {
          if ( v14 > 0x7FFFFFFE )
          {
            v12 = -2147024809;
            if ( v14 != -1 )
              *Heap = 0;
          }
          else
          {
            v17 = Heap;
            v18 = (char *)((char *)String1 - (char *)Heap);
            while ( v16 != 1 )
            {
              v19 = *(_WORD *)((char *)v17 + (_QWORD)v18);
              if ( !v19 )
                break;
              *v17 = v19;
              --v16;
              ++v17;
            }
            v20 = v17 - 1;
            if ( v16 )
              v20 = v17;
            v12 = v16 == 0 ? 0x8007007A : 0;
            *v20 = 0;
          }
        }
      }
      if ( (v12 & 0x80000000) != 0 )
        goto LABEL_39;
      *a3 = Heap;
      Heap = 0;
    }
    else
    {
      v12 = 0;
    }
    if ( !a2 )
      return v12;
    *a2 = 1;
LABEL_39:
    if ( Heap )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, Heap);
    }
    return v12;
  }
  return (unsigned int)-2147024883;
}

```

## disassembly

```asm
0x18000ed90  mov     [rsp+arg_0], rbx
0x18000ed95  mov     [rsp+arg_8], rbp
0x18000ed9a  mov     [rsp+arg_10], rsi
0x18000ed9f  push    rdi
0x18000eda0  push    r12
0x18000eda2  push    r13
0x18000eda4  push    r14
0x18000eda6  push    r15
0x18000eda8  sub     rsp, 20h
0x18000edac  xor     r13d, r13d
0x18000edaf  mov     r12, r8
0x18000edb2  mov     r15, rdx
0x18000edb5  mov     rsi, rcx
0x18000edb8  test    rcx, rcx
0x18000edbb  jnz     short loc_18000EDC7
0x18000edbd  mov     eax, 80070057h
0x18000edc2  jmp     loc_18000EF96
0x18000edc7  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000edcb  mov     rax, r14
0x18000edce  inc     rax
0x18000edd1  cmp     [rcx+rax*2], r13w
0x18000edd6  jnz     short loc_18000EDCE
0x18000edd8  cmp     rax, 2
0x18000eddc  jb      loc_18000EF80
0x18000ede2  mov     r8d, 2; MaxCount
0x18000ede8  lea     rdx, asc_18001451C; "\\\\"
0x18000edef  call    _wcsnicmp_0
0x18000edf4  test    eax, eax
0x18000edf6  jnz     loc_18000EF80
0x18000edfc  mov     rax, r14
0x18000edff  inc     rax
0x18000ee02  cmp     [rsi+rax*2], r13w
0x18000ee07  jnz     short loc_18000EDFF
0x18000ee09  cmp     rax, 8
0x18000ee0d  jb      short loc_18000EE2E
0x18000ee0f  mov     r8d, 8; MaxCount
0x18000ee15  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x18000ee1c  mov     rcx, rsi; String1
0x18000ee1f  call    _wcsnicmp_0
0x18000ee24  test    eax, eax
0x18000ee26  mov     ecx, r13d
0x18000ee29  setz    cl
0x18000ee2c  jmp     short loc_18000EE31
0x18000ee2e  mov     ecx, r13d
0x18000ee31  neg     ecx
0x18000ee33  mov     ebx, 5Ch ; '\'
0x18000ee38  mov     edx, ebx; Ch
0x18000ee3a  sbb     rcx, rcx
0x18000ee3d  and     ecx, 0Ch
0x18000ee40  add     rcx, 4
0x18000ee44  add     rcx, rsi; Str
0x18000ee47  call    wcschr_0
0x18000ee4c  test    rax, rax
0x18000ee4f  jnz     short loc_18000EE5B
0x18000ee51  mov     ebx, 8007000Dh
0x18000ee56  jmp     loc_18000EF94
0x18000ee5b  mov     rdi, r13
0x18000ee5e  mov     rbp, r14
0x18000ee61  inc     rbp
0x18000ee64  cmp     [rsi+rbp*2], r13w
0x18000ee69  jnz     short loc_18000EE61
0x18000ee6b  mov     edx, ebx; Ch
0x18000ee6d  lea     rcx, [rax+2]; Str
0x18000ee71  call    wcschr_0
0x18000ee76  test    rax, rax
0x18000ee79  jz      short loc_18000EE84
0x18000ee7b  mov     rbp, rax
0x18000ee7e  sub     rbp, rsi
0x18000ee81  sar     rbp, 1
0x18000ee84  test    r12, r12
0x18000ee87  jz      loc_18000EF4A
0x18000ee8d  mov     ebx, 8007000Eh
0x18000ee92  inc     r14
0x18000ee95  cmp     [rsi+r14*2], r13w
0x18000ee9a  jnz     short loc_18000EE92
0x18000ee9c  cmp     rbp, r14
0x18000ee9f  ja      short loc_18000EEE6
0x18000eea1  mov     rcx, gs:60h
0x18000eeaa  lea     r14, [rbp+1]
0x18000eeae  lea     r8, [r14+r14]; Size
0x18000eeb2  mov     edx, 8; Flags
0x18000eeb7  mov     rcx, [rcx+30h]; HeapHandle
0x18000eebb  call    cs:__imp_RtlAllocateHeap
0x18000eec2  nop     dword ptr [rax+rax+00h]
0x18000eec7  mov     rdi, rax
0x18000eeca  test    rax, rax
0x18000eecd  jz      short loc_18000EEEB
0x18000eecf  lea     rcx, [r14-1]
0x18000eed3  mov     eax, 7FFFFFFEh
0x18000eed8  cmp     rcx, rax
0x18000eedb  ja      short loc_18000EF3A
0x18000eedd  cmp     rbp, rax
0x18000eee0  jbe     short loc_18000EEF8
0x18000eee2  mov     [rdi], r13w
0x18000eee6  mov     ebx, 80070057h
0x18000eeeb  test    ebx, ebx
0x18000eeed  js      short loc_18000EF59
0x18000eeef  mov     [r12], rdi
0x18000eef3  mov     rdi, r13
0x18000eef6  jmp     short loc_18000EF4D
0x18000eef8  mov     rcx, rdi
0x18000eefb  sub     rsi, rdi
0x18000eefe  lea     rdx, [r14-1]
0x18000ef02  test    rdx, rdx
0x18000ef05  jz      short loc_18000EF1C
0x18000ef07  movzx   eax, word ptr [rsi+rcx]
0x18000ef0b  test    ax, ax
0x18000ef0e  jz      short loc_18000EF1C
0x18000ef10  mov     [rcx], ax
0x18000ef13  mov     r14, rdx
0x18000ef16  add     rcx, 2
0x18000ef1a  jmp     short loc_18000EEFE
0x18000ef1c  test    r14, r14
0x18000ef1f  lea     rax, [rcx-2]
0x18000ef23  cmovnz  rax, rcx
0x18000ef27  neg     r14
0x18000ef2a  sbb     ebx, ebx
0x18000ef2c  not     ebx
0x18000ef2e  and     ebx, 8007007Ah
0x18000ef34  mov     [rax], r13w
0x18000ef38  jmp     short loc_18000EEEB
0x18000ef3a  mov     ebx, 80070057h
0x18000ef3f  test    r14, r14
0x18000ef42  jz      short loc_18000EEEB
0x18000ef44  mov     [rdi], r13w
0x18000ef48  jmp     short loc_18000EEEB
0x18000ef4a  mov     ebx, r13d
0x18000ef4d  test    r15, r15
0x18000ef50  jz      short loc_18000EF94
0x18000ef52  mov     dword ptr [r15], 1
0x18000ef59  test    rdi, rdi
0x18000ef5c  jz      short loc_18000EF94
0x18000ef5e  call    cs:__imp_GetProcessHeap
0x18000ef65  nop     dword ptr [rax+rax+00h]
0x18000ef6a  mov     r8, rdi; lpMem
0x18000ef6d  xor     edx, edx; dwFlags
0x18000ef6f  mov     rcx, rax; hHeap
0x18000ef72  call    cs:__imp_HeapFree
0x18000ef79  nop     dword ptr [rax+rax+00h]
0x18000ef7e  jmp     short loc_18000EF94
0x18000ef80  mov     ebx, r13d
0x18000ef83  test    r15, r15
0x18000ef86  jz      short loc_18000EF8B
0x18000ef88  mov     [r15], r13d
0x18000ef8b  test    r12, r12
0x18000ef8e  jz      short loc_18000EF94
0x18000ef90  mov     [r12], r13
0x18000ef94  mov     eax, ebx
0x18000ef96  mov     rbx, [rsp+48h+arg_0]
0x18000ef9b  mov     rbp, [rsp+48h+arg_8]
0x18000efa0  mov     rsi, [rsp+48h+arg_10]
0x18000efa5  add     rsp, 20h
0x18000efa9  pop     r15
0x18000efab  pop     r14
0x18000efad  pop     r13
0x18000efaf  pop     r12
0x18000efb1  pop     rdi
0x18000efb2  retn
```
