# VbsDebug::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18006aa80`
- end: `0x18006ab45`
- name: `?GetIDsOfNames@VbsDebug@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `197`
- prototype: `__int64 __fastcall(VbsDebug *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18006aa80`
- `0x180079436`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18006aacf`
- `msvcrt!_wcsicmp` at `0x18006aaf7`
- `msvcrt!_wcsicmp` at `0x18006aacf`
- `msvcrt!_wcsicmp` at `0x18006aaf7`

## string_xrefs

- `0x18006aac6`: `WriteLine`
- `0x18006aaee`: `Write`

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
0x18006aa80  push    rbx
0x18006aa82  push    rsi
0x18006aa83  push    rdi
0x18006aa84  push    r14
0x18006aa86  push    r15
0x18006aa88  sub     rsp, 20h
0x18006aa8c  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18006aa93  mov     esi, r9d
0x18006aa96  mov     r15, r8
0x18006aa99  sub     rax, [rdx]
0x18006aa9c  jnz     short loc_18006AAA9
0x18006aa9e  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18006aaa5  sub     rax, [rdx+8]
0x18006aaa9  test    rax, rax
0x18006aaac  jz      short loc_18006AAB8
0x18006aaae  mov     eax, 80020001h
0x18006aab3  jmp     loc_18006AB38
0x18006aab8  test    esi, esi
0x18006aaba  jnz     short loc_18006AAC3
0x18006aabc  mov     edi, 80020006h
0x18006aac1  jmp     short loc_18006AB36
0x18006aac3  mov     rcx, [r8]; String1
0x18006aac6  lea     rdx, aWriteline; "WriteLine"
0x18006aacd  xor     edi, edi
0x18006aacf  call    cs:__imp__wcsicmp
0x18006aad6  nop     dword ptr [rax+rax+00h]
0x18006aadb  mov     r14, [rsp+48h+arg_28]
0x18006aae0  test    eax, eax
0x18006aae2  jnz     short loc_18006AAEB
0x18006aae4  lea     ebx, [rdi+1]
0x18006aae7  mov     eax, ebx
0x18006aae9  jmp     short loc_18006AB0D
0x18006aaeb  mov     rcx, [r15]; String1
0x18006aaee  lea     rdx, aWrite; "Write"
0x18006aaf5  xor     ebx, ebx
0x18006aaf7  call    cs:__imp__wcsicmp
0x18006aafe  nop     dword ptr [rax+rax+00h]
0x18006ab03  test    eax, eax
0x18006ab05  jnz     short loc_18006AB16
0x18006ab07  lea     ebx, [rax+1]
0x18006ab0a  lea     eax, [rbx+1]
0x18006ab0d  mov     rcx, r14
0x18006ab10  mov     [rcx], eax
0x18006ab12  cmp     esi, ebx
0x18006ab14  jbe     short loc_18006AB36
0x18006ab16  mov     edi, 80020006h
0x18006ab1b  cmp     ebx, esi
0x18006ab1d  jnb     short loc_18006AB36
0x18006ab1f  sub     esi, ebx
0x18006ab21  mov     ecx, ebx
0x18006ab23  mov     r8d, esi
0x18006ab26  or      edx, 0FFFFFFFFh; Val
0x18006ab29  shl     r8, 2; Size
0x18006ab2d  lea     rcx, [r14+rcx*4]; void *
0x18006ab31  call    memset_0
0x18006ab36  mov     eax, edi
0x18006ab38  add     rsp, 20h
0x18006ab3c  pop     r15
0x18006ab3e  pop     r14
0x18006ab40  pop     rdi
0x18006ab41  pop     rsi
0x18006ab42  pop     rbx
0x18006ab43  retn
```
