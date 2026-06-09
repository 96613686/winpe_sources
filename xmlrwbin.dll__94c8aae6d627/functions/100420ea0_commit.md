# _commit

- ea: `0x100420ea0`
- end: `0x100420f31`
- name: `_commit`
- size: `145`
- prototype: `int __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10041eedc`

## callees

- `0x10041c048`
- `0x10041c1a8`
- `0x100420e0c`
- `0x100420ea0`

## pseudocode

```c
int __cdecl commit(int FileHandle)
{
  int *v2; // [rsp+20h] [rbp-18h] BYREF
  int v3; // [rsp+40h] [rbp+8h] BYREF
  char v4; // [rsp+48h] [rbp+10h] BYREF
  int v5; // [rsp+50h] [rbp+18h] BYREF
  int v6; // [rsp+58h] [rbp+20h] BYREF

  v3 = FileHandle;
  if ( FileHandle == -2 )
  {
    *errno() = 9;
  }
  else
  {
    if ( FileHandle >= 0
      && FileHandle < (unsigned int)nhandle
      && (*(_BYTE *)(_pioinfo[(__int64)FileHandle >> 6] + 72LL * (FileHandle & 0x3F) + 56) & 1) != 0 )
    {
      v5 = FileHandle;
      v6 = FileHandle;
      v2 = &v3;
      return ((__int64 (__fastcall *)(char *, int *, int **, int *))_crt_seh_guarded_call_int_::operator()__lambda_a37b2b86f63e897a80ea819b0eb08c01___lambda_38ce7e780aa69e748d6df282ebc68efe_____lambda_99fb1378e971ab6e7edea83e3a7a83a2___)(
               &v4,
               &v6,
               &v2,
               &v5);
    }
    *errno() = 9;
    invalid_parameter_noinfo();
  }
  return -1;
}

```

## disassembly

```asm
0x100420ea0  mov     [rsp+arg_0], ecx
0x100420ea4  sub     rsp, 38h
0x100420ea8  movsxd  rdx, ecx
0x100420eab  cmp     edx, 0FFFFFFFEh
0x100420eae  jnz     short loc_100420EBD
0x100420eb0  call    _errno
0x100420eb5  mov     dword ptr [rax], 9
0x100420ebb  jmp     short loc_100420F29
0x100420ebd  test    ecx, ecx
0x100420ebf  js      short loc_100420F19
0x100420ec1  cmp     edx, cs:_nhandle
0x100420ec7  jnb     short loc_100420F19
0x100420ec9  mov     rcx, rdx
0x100420ecc  lea     r8, __pioinfo
0x100420ed3  and     ecx, 3Fh
0x100420ed6  mov     rax, rdx
0x100420ed9  sar     rax, 6
0x100420edd  lea     rcx, [rcx+rcx*8]
0x100420ee1  mov     rax, [r8+rax*8]
0x100420ee5  test    byte ptr [rax+rcx*8+38h], 1
0x100420eea  jz      short loc_100420F19
0x100420eec  lea     rax, [rsp+38h+arg_0]
0x100420ef1  mov     [rsp+38h+arg_10], edx
0x100420ef5  mov     [rsp+38h+arg_18], edx
0x100420ef9  lea     r9, [rsp+38h+arg_10]
0x100420efe  lea     rdx, [rsp+38h+arg_18]
0x100420f03  mov     [rsp+38h+var_18], rax
0x100420f08  lea     r8, [rsp+38h+var_18]
0x100420f0d  lea     rcx, [rsp+38h+arg_8]
0x100420f12  call    __crt_seh_guarded_call_int___operator____lambda_a37b2b86f63e897a80ea819b0eb08c01___lambda_38ce7e780aa69e748d6df282ebc68efe_____lambda_99fb1378e971ab6e7edea83e3a7a83a2___
0x100420f17  jmp     short loc_100420F2C
0x100420f19  call    _errno
0x100420f1e  mov     dword ptr [rax], 9
0x100420f24  call    _invalid_parameter_noinfo
0x100420f29  or      eax, 0FFFFFFFFh
0x100420f2c  add     rsp, 38h
0x100420f30  retn
```
