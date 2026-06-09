# sprintf_sfn(char *,unsigned __int64,char const *,...)

- ea: `0x1800122b0`
- end: `0x180012304`
- name: `?sprintf_sfn@@YAXPEAD_KPEBDZZ`
- size: `84`
- prototype: `void(char *, unsigned __int64, const char *, ...)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fa80`
- `0x18000fba4`
- `0x18000fd80`
- `0x18000ff64`
- `0x180010130`
- `0x1800102e0`
- `0x180010400`

## callees

- `0x1800122b0`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x1800122e6`
- `msvcrt!_vsnprintf` at `0x1800122e6`

## pseudocode

```c
void sprintf_sfn(char *a1, __int64 a2, const char *a3, ...)
{
  unsigned __int64 v4; // rbx
  int v5; // eax
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  *a1 = 0;
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v4 = a2 - 1;
    v5 = _vsnprintf(a1, a2 - 1, a3, va);
    if ( v5 < 0 || v5 >= v4 )
      a1[v4] = 0;
  }
}

```

## disassembly

```asm
0x1800122b0  mov     rax, rsp
0x1800122b3  mov     [rax+18h], r8
0x1800122b7  mov     [rax+20h], r9
0x1800122bb  push    rbx
0x1800122bc  push    rdi
0x1800122bd  sub     rsp, 38h
0x1800122c1  mov     qword ptr [rax-28h], 0
0x1800122c9  lea     r9, [rax+20h]; ArgList
0x1800122cd  lea     rax, [rdx-1]
0x1800122d1  mov     byte ptr [rcx], 0
0x1800122d4  mov     rdi, rcx
0x1800122d7  cmp     rax, 7FFFFFFEh
0x1800122dd  ja      short loc_1800122FD
0x1800122df  lea     rbx, [rdx-1]
0x1800122e3  mov     rdx, rbx; BufferCount
0x1800122e6  call    cs:__imp__vsnprintf
0x1800122ec  test    eax, eax
0x1800122ee  js      short loc_1800122F9
0x1800122f0  cdqe
0x1800122f2  cmp     rax, rbx
0x1800122f5  ja      short loc_1800122F9
0x1800122f7  jnz     short loc_1800122FD
0x1800122f9  mov     byte ptr [rbx+rdi], 0
0x1800122fd  add     rsp, 38h
0x180012301  pop     rdi
0x180012302  pop     rbx
0x180012303  retn
```
