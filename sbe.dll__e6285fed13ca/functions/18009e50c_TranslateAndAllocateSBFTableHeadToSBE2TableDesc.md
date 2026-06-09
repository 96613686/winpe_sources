# TranslateAndAllocateSBFTableHeadToSBE2TableDesc

- ea: `0x18009e50c`
- end: `0x18009e5fa`
- name: `TranslateAndAllocateSBFTableHeadToSBE2TableDesc`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18009d630`

## callees

- `0x180002e68`
- `0x18000624c`
- `0x18009e50c`
- `0x1800b33f9`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18009e572`
- `ole32!CoTaskMemAlloc` at `0x18009e5c2`
- `ole32!CoTaskMemAlloc` at `0x18009e572`
- `ole32!CoTaskMemAlloc` at `0x18009e5c2`
- `ole32!CoTaskMemFree` at `0x18009e53c`
- `ole32!CoTaskMemFree` at `0x18009e545`
- `ole32!CoTaskMemFree` at `0x18009e53c`
- `ole32!CoTaskMemFree` at `0x18009e545`

## pseudocode

```c
__int64 __fastcall TranslateAndAllocateSBFTableHeadToSBE2TableDesc(unsigned int a1, __int64 a2, LPVOID *a3)
{
  int v6; // ebx
  int v8; // r8d
  unsigned __int16 *v9; // rax
  SIZE_T v10; // rcx
  void *v11; // rcx

  *a3 = 0;
  if ( a1 >= 0x50 )
  {
    v6 = StringCchLengthW((const unsigned __int16 *)(a2 + 16), 0x20u, 0);
    if ( v6 >= 0 )
    {
      v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(v8 + 88));
      *a3 = v9;
      if ( v9 )
      {
        v6 = StringCchCopyW(v9, 0x20u, (const unsigned __int16 *)(a2 + 16));
        if ( v6 < 0 )
          goto LABEL_3;
        *((_DWORD *)*a3 + 16) = *(_DWORD *)(a2 + 4);
        *((_DWORD *)*a3 + 17) = *(_DWORD *)a2;
        *((_DWORD *)*a3 + 18) = a1 - 80;
        v10 = *((unsigned int *)*a3 + 18);
        if ( !(_DWORD)v10 )
        {
          *((_QWORD *)*a3 + 10) = 0;
          return (unsigned int)v6;
        }
        *((_QWORD *)*a3 + 10) = CoTaskMemAlloc(v10);
        v11 = (void *)*((_QWORD *)*a3 + 10);
        if ( v11 )
        {
          memcpy_0(v11, (const void *)(a2 + 80), *((unsigned int *)*a3 + 18));
          return (unsigned int)v6;
        }
      }
      v6 = -2147024882;
    }
  }
  else
  {
    v6 = -2147024809;
  }
LABEL_3:
  if ( *a3 )
    CoTaskMemFree(*((LPVOID *)*a3 + 10));
  CoTaskMemFree(*a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009e50c  push    rbx
0x18009e50e  push    rbp
0x18009e50f  push    rsi
0x18009e510  push    rdi
0x18009e511  push    r14
0x18009e513  sub     rsp, 20h
0x18009e517  mov     qword ptr [r8], 0
0x18009e51e  mov     rdi, r8
0x18009e521  mov     rsi, rdx
0x18009e524  mov     ebp, ecx
0x18009e526  cmp     ecx, 50h ; 'P'
0x18009e529  jnb     short loc_18009E558
0x18009e52b  mov     ebx, 80070057h
0x18009e530  mov     rcx, [rdi]
0x18009e533  test    rcx, rcx
0x18009e536  jz      short loc_18009E542
0x18009e538  mov     rcx, [rcx+50h]; pv
0x18009e53c  call    cs:__imp_CoTaskMemFree
0x18009e542  mov     rcx, [rdi]; pv
0x18009e545  call    cs:__imp_CoTaskMemFree
0x18009e54b  mov     eax, ebx
0x18009e54d  add     rsp, 20h
0x18009e551  pop     r14
0x18009e553  pop     rdi
0x18009e554  pop     rsi
0x18009e555  pop     rbp
0x18009e556  pop     rbx
0x18009e557  retn
0x18009e558  xor     r8d, r8d; unsigned __int64 *
0x18009e55b  lea     rcx, [rsi+10h]; unsigned __int16 *
0x18009e55f  lea     edx, [r8+20h]; unsigned __int64
0x18009e563  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009e568  mov     ebx, eax
0x18009e56a  test    eax, eax
0x18009e56c  js      short loc_18009E530
0x18009e56e  lea     ecx, [r8+58h]; cb
0x18009e572  call    cs:__imp_CoTaskMemAlloc
0x18009e578  mov     [rdi], rax
0x18009e57b  test    rax, rax
0x18009e57e  jnz     short loc_18009E587
0x18009e580  mov     ebx, 8007000Eh
0x18009e585  jmp     short loc_18009E530
0x18009e587  lea     r8, [rsi+10h]; unsigned __int16 *
0x18009e58b  mov     edx, 20h ; ' '; unsigned __int64
0x18009e590  mov     rcx, rax; unsigned __int16 *
0x18009e593  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009e598  mov     ebx, eax
0x18009e59a  test    eax, eax
0x18009e59c  js      short loc_18009E530
0x18009e59e  mov     ecx, [rsi+4]
0x18009e5a1  mov     rdx, [rdi]
0x18009e5a4  mov     [rdx+40h], ecx
0x18009e5a7  mov     rdx, [rdi]
0x18009e5aa  mov     ecx, [rsi]
0x18009e5ac  mov     [rdx+44h], ecx
0x18009e5af  lea     edx, [rbp-50h]
0x18009e5b2  mov     rcx, [rdi]
0x18009e5b5  mov     [rcx+48h], edx
0x18009e5b8  mov     rax, [rdi]
0x18009e5bb  mov     ecx, [rax+48h]; cb
0x18009e5be  test    ecx, ecx
0x18009e5c0  jz      short loc_18009E5ED
0x18009e5c2  call    cs:__imp_CoTaskMemAlloc
0x18009e5c8  mov     rcx, [rdi]
0x18009e5cb  mov     [rcx+50h], rax
0x18009e5cf  mov     rax, [rdi]
0x18009e5d2  mov     rcx, [rax+50h]; void *
0x18009e5d6  test    rcx, rcx
0x18009e5d9  jz      short loc_18009E580
0x18009e5db  mov     r8d, [rax+48h]; Size
0x18009e5df  lea     rdx, [rsi+50h]; Src
0x18009e5e3  call    memcpy_0
0x18009e5e8  jmp     loc_18009E54B
0x18009e5ed  mov     qword ptr [rax+50h], 0
0x18009e5f5  jmp     loc_18009E54B
```
