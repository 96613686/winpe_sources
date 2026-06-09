# VbsDebug::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180068960`
- end: `0x180068a15`
- name: `?GetIDsOfNames@VbsDebug@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `181`
- prototype: `__int64 __fastcall(VbsDebug *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180068960`
- `0x180076746`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800689ac`
- `msvcrt!_wcsicmp` at `0x1800689ce`
- `msvcrt!_wcsicmp` at `0x1800689ac`
- `msvcrt!_wcsicmp` at `0x1800689ce`

## string_xrefs

- `0x1800689a3`: `WriteLine`
- `0x1800689c5`: `Write`

## pseudocode

```c
__int64 __fastcall VbsDebug::GetIDsOfNames(
        VbsDebug *this,
        const struct _GUID *a2,
        const wchar_t **a3,
        unsigned int a4,
        unsigned int a5,
        int *a6)
{
  __int64 v8; // rax
  unsigned int v10; // edi
  unsigned int v11; // ebx
  int v12; // eax

  v8 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a2->Data1 )
    v8 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)a2->Data4;
  if ( v8 )
    return 2147614721LL;
  if ( a4 )
  {
    v10 = 0;
    if ( _wcsicmp(*a3, L"WriteLine") )
    {
      v11 = 0;
      if ( _wcsicmp(*a3, L"Write") )
        goto LABEL_12;
      v11 = 1;
      v12 = 2;
    }
    else
    {
      v11 = 1;
      v12 = 1;
    }
    *a6 = v12;
    if ( a4 <= 1 )
      return v10;
LABEL_12:
    v10 = -2147352570;
    if ( v11 < a4 )
      memset_0(&a6[v11], -1, 4LL * (a4 - v11));
    return v10;
  }
  return (unsigned int)-2147352570;
}

```

## disassembly

```asm
0x180068960  push    rbx
0x180068962  push    rsi
0x180068963  push    rdi
0x180068964  push    r14
0x180068966  push    r15
0x180068968  sub     rsp, 20h
0x18006896c  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180068973  mov     esi, r9d
0x180068976  mov     r15, r8
0x180068979  sub     rax, [rdx]
0x18006897c  jnz     short loc_180068989
0x18006897e  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180068985  sub     rax, [rdx+8]
0x180068989  test    rax, rax
0x18006898c  jz      short loc_180068995
0x18006898e  mov     eax, 80020001h
0x180068993  jmp     short loc_180068A09
0x180068995  test    esi, esi
0x180068997  jnz     short loc_1800689A0
0x180068999  mov     edi, 80020006h
0x18006899e  jmp     short loc_180068A07
0x1800689a0  mov     rcx, [r8]; String1
0x1800689a3  lea     rdx, aWriteline; "WriteLine"
0x1800689aa  xor     edi, edi
0x1800689ac  call    cs:__imp__wcsicmp
0x1800689b2  mov     r14, [rsp+48h+arg_28]
0x1800689b7  test    eax, eax
0x1800689b9  jnz     short loc_1800689C2
0x1800689bb  lea     ebx, [rdi+1]
0x1800689be  mov     eax, ebx
0x1800689c0  jmp     short loc_1800689DE
0x1800689c2  mov     rcx, [r15]; String1
0x1800689c5  lea     rdx, aWrite; "Write"
0x1800689cc  xor     ebx, ebx
0x1800689ce  call    cs:__imp__wcsicmp
0x1800689d4  test    eax, eax
0x1800689d6  jnz     short loc_1800689E7
0x1800689d8  lea     ebx, [rax+1]
0x1800689db  lea     eax, [rbx+1]
0x1800689de  mov     rcx, r14
0x1800689e1  mov     [rcx], eax
0x1800689e3  cmp     esi, ebx
0x1800689e5  jbe     short loc_180068A07
0x1800689e7  mov     edi, 80020006h
0x1800689ec  cmp     ebx, esi
0x1800689ee  jnb     short loc_180068A07
0x1800689f0  sub     esi, ebx
0x1800689f2  mov     ecx, ebx
0x1800689f4  mov     r8d, esi
0x1800689f7  or      edx, 0FFFFFFFFh; Val
0x1800689fa  shl     r8, 2; Size
0x1800689fe  lea     rcx, [r14+rcx*4]; void *
0x180068a02  call    memset_0
0x180068a07  mov     eax, edi
0x180068a09  add     rsp, 20h
0x180068a0d  pop     r15
0x180068a0f  pop     r14
0x180068a11  pop     rdi
0x180068a12  pop     rsi
0x180068a13  pop     rbx
0x180068a14  retn
```
