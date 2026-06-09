# _write_internal

- ea: `0x100434d04`
- end: `0x100434e21`
- name: `_write_internal`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1004313d8`

## callees

- `0x10042e504`
- `0x100434220`
- `0x100434250`
- `0x100434d04`
- `0x100434e28`

## pseudocode

```c
__int64 __fastcall write_internal(unsigned int a1, _BYTE *a2, unsigned int a3, __int64 a4)
{
  BOOL v8; // eax
  __int64 v9; // r15
  unsigned int v10; // r14d

  if ( a1 == -2 )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return 0xFFFFFFFFLL;
  }
  v8 = (a1 & 0x80000000) == 0 && a1 < nhandle;
  if ( !v8 || (v9 = (__int64)(int)a1 >> 6, (*(_BYTE *)(_pioinfo[v9] + 72LL * (a1 & 0x3F) + 56) & 1) == 0) )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  _acrt_lowio_lock_fh(a1);
  v10 = -1;
  if ( (*(_BYTE *)(_pioinfo[v9] + 72LL * (a1 & 0x3F) + 56) & 1) != 0 )
  {
    v10 = write_nolock(a1, a2, a3, a4);
  }
  else
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
  }
  _acrt_lowio_unlock_fh(a1);
  return v10;
}

```

## disassembly

```asm
0x100434d04  mov     [rsp+arg_10], rbx
0x100434d09  mov     [rsp+arg_8], rdx
0x100434d0e  mov     [rsp+arg_0], ecx
0x100434d12  push    rsi
0x100434d13  push    r12
0x100434d15  push    r13
0x100434d17  push    r14
0x100434d19  push    r15
0x100434d1b  sub     rsp, 30h
0x100434d1f  mov     rbx, r9
0x100434d22  mov     r13d, r8d
0x100434d25  movsxd  rsi, ecx
0x100434d28  cmp     esi, 0FFFFFFFEh
0x100434d2b  jnz     short loc_100434D5A
0x100434d2d  mov     byte ptr [r9+38h], 1
0x100434d32  and     dword ptr [r9+34h], 0
0x100434d37  mov     byte ptr [r9+30h], 1
0x100434d3c  mov     dword ptr [r9+2Ch], 9
0x100434d44  or      eax, 0FFFFFFFFh
0x100434d47  mov     rbx, [rsp+58h+arg_10]
0x100434d4c  add     rsp, 30h
0x100434d50  pop     r15
0x100434d52  pop     r14
0x100434d54  pop     r13
0x100434d56  pop     r12
0x100434d58  pop     rsi
0x100434d59  retn
0x100434d5a  test    ecx, ecx
0x100434d5c  js      short loc_100434D6D
0x100434d5e  cmp     esi, cs:_nhandle
0x100434d64  jnb     short loc_100434D6D
0x100434d66  mov     eax, 1
0x100434d6b  jmp     short loc_100434D6F
0x100434d6d  xor     eax, eax
0x100434d6f  test    eax, eax
0x100434d71  jnz     short loc_100434DA6
0x100434d73  mov     byte ptr [r9+38h], 1
0x100434d78  and     dword ptr [r9+34h], 0
0x100434d7d  mov     byte ptr [r9+30h], 1
0x100434d82  mov     dword ptr [r9+2Ch], 9
0x100434d8a  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x100434d8f  and     [rsp+58h+var_38], 0
0x100434d95  xor     r9d, r9d; LineNo
0x100434d98  xor     r8d, r8d; FileName
0x100434d9b  xor     edx, edx; FunctionName
0x100434d9d  xor     ecx, ecx; Expression
0x100434d9f  call    _invalid_parameter_internal
0x100434da4  jmp     short loc_100434D44
0x100434da6  mov     rax, rsi
0x100434da9  mov     r15, rsi
0x100434dac  sar     r15, 6
0x100434db0  lea     rcx, __pioinfo
0x100434db7  and     eax, 3Fh
0x100434dba  lea     r12, [rax+rax*8]
0x100434dbe  mov     rax, [rcx+r15*8]
0x100434dc2  test    byte ptr [rax+r12*8+38h], 1
0x100434dc8  jz      short loc_100434D73
0x100434dca  mov     ecx, esi
0x100434dcc  call    __acrt_lowio_lock_fh
0x100434dd1  or      r14d, 0FFFFFFFFh
0x100434dd5  lea     rax, __pioinfo
0x100434ddc  mov     rax, [rax+r15*8]
0x100434de0  test    byte ptr [rax+r12*8+38h], 1
0x100434de6  jnz     short loc_100434DFD
0x100434de8  mov     byte ptr [rbx+30h], 1
0x100434dec  mov     dword ptr [rbx+2Ch], 9
0x100434df3  mov     byte ptr [rbx+38h], 1
0x100434df7  and     dword ptr [rbx+34h], 0
0x100434dfb  jmp     short loc_100434E12
0x100434dfd  mov     r9, rbx
0x100434e00  mov     r8d, r13d
0x100434e03  mov     rdx, [rsp+58h+arg_8]
0x100434e08  mov     ecx, esi
0x100434e0a  call    _write_nolock
0x100434e0f  mov     r14d, eax
0x100434e12  mov     ecx, esi
0x100434e14  call    __acrt_lowio_unlock_fh
0x100434e19  mov     eax, r14d
0x100434e1c  jmp     loc_100434D47
0x10043acb6  push    rbp
0x10043acb8  sub     rsp, 30h
0x10043acbc  mov     rbp, rdx
0x10043acbf  mov     ecx, [rbp+60h]
0x10043acc2  add     rsp, 30h
0x10043acc6  pop     rbp
0x10043acc7  jmp     __acrt_lowio_unlock_fh
```
