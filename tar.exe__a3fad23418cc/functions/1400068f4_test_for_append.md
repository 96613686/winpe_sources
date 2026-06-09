# test_for_append

- ea: `0x1400068f4`
- end: `0x1400069a1`
- name: `test_for_append`
- size: `173`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400063bc`
- `0x140006650`

## callees

- `0x140001340`
- `0x1400068f4`
- `0x1400071a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stat64i32` at `0x14000693f`
- `api-ms-win-crt-private-l1-1-0!_o__stat64i32` at `0x14000693f`

## pseudocode

```c
int __fastcall test_for_append(const char **a1)
{
  const char *v1; // rax
  const char *v3; // rcx
  int result; // eax
  _stat64i32 Stat; // [rsp+20h] [rbp-48h] BYREF

  v1 = a1[19];
  memset(&Stat, 0, sizeof(Stat));
  if ( !*(_QWORD *)v1 && !a1[2] )
    lafe_errc(1, 0, (__int64)"no files or directories specified");
  v3 = *a1;
  if ( !v3 )
    lafe_errc(1, 0, (__int64)"Cannot append to stdout.");
  result = _stat64i32(v3, &Stat);
  if ( !result )
  {
    result = 0x8000;
    if ( (Stat.st_mode & 0x8000u) == 0 )
      lafe_errc(1, 0, (__int64)"Cannot append to %s: not a regular file.", *a1);
  }
  return result;
}

```

## disassembly

```asm
0x1400068f4  push    rbx
0x1400068f6  sub     rsp, 60h
0x1400068fa  mov     rax, cs:__security_cookie
0x140006901  xor     rax, rsp
0x140006904  mov     [rsp+68h+var_18], rax
0x140006909  mov     rax, [rcx+98h]
0x140006910  xorps   xmm0, xmm0
0x140006913  movups  xmmword ptr [rsp+68h+Stat.st_dev], xmm0
0x140006918  mov     rbx, rcx
0x14000691b  movups  xmmword ptr [rsp+68h+Stat.st_rdev], xmm0
0x140006920  movups  xmmword ptr [rsp+68h+Stat.st_mtime], xmm0
0x140006925  cmp     qword ptr [rax], 0
0x140006929  jnz     short loc_140006932
0x14000692b  cmp     qword ptr [rcx+10h], 0
0x140006930  jz      short loc_140006968
0x140006932  mov     rcx, [rcx]; FileName
0x140006935  test    rcx, rcx
0x140006938  jz      short loc_14000697A
0x14000693a  lea     rdx, [rsp+68h+Stat]; Stat
0x14000693f  call    cs:__imp__stat64i32
0x140006945  test    eax, eax
0x140006947  jnz     short loc_140006955
0x140006949  mov     eax, 8000h
0x14000694e  test    [rsp+68h+Stat.st_mode], ax
0x140006953  jz      short loc_14000698C
0x140006955  mov     rcx, [rsp+68h+var_18]
0x14000695a  xor     rcx, rsp; StackCookie
0x14000695d  call    __security_check_cookie
0x140006962  add     rsp, 60h
0x140006966  pop     rbx
0x140006967  retn
0x140006968  xor     edx, edx
0x14000696a  lea     r8, aNoFilesOrDirec; "no files or directories specified"
0x140006971  lea     ecx, [rdx+1]; Code
0x140006974  call    lafe_errc
0x14000697a  xor     edx, edx
0x14000697c  lea     r8, aCannotAppendTo; "Cannot append to stdout."
0x140006983  lea     ecx, [rdx+1]; Code
0x140006986  call    lafe_errc
0x14000698c  mov     r9, [rbx]
0x14000698f  lea     r8, aCannotAppendTo_0; "Cannot append to %s: not a regular file"...
0x140006996  xor     edx, edx
0x140006998  lea     ecx, [rdx+1]; Code
0x14000699b  call    lafe_errc
```
