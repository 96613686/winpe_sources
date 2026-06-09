# _write_internal

- ea: `0x100421754`
- end: `0x100421871`
- name: `_write_internal`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10041ee48`

## callees

- `0x10041bf74`
- `0x100420c70`
- `0x100420ca0`
- `0x100421754`
- `0x100421878`

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
0x100421754  mov     [rsp+arg_10], rbx
0x100421759  mov     [rsp+arg_8], rdx
0x10042175e  mov     [rsp+arg_0], ecx
0x100421762  push    rsi
0x100421763  push    r12
0x100421765  push    r13
0x100421767  push    r14
0x100421769  push    r15
0x10042176b  sub     rsp, 30h
0x10042176f  mov     rbx, r9
0x100421772  mov     r13d, r8d
0x100421775  movsxd  rsi, ecx
0x100421778  cmp     esi, 0FFFFFFFEh
0x10042177b  jnz     short loc_1004217AA
0x10042177d  mov     byte ptr [r9+38h], 1
0x100421782  and     dword ptr [r9+34h], 0
0x100421787  mov     byte ptr [r9+30h], 1
0x10042178c  mov     dword ptr [r9+2Ch], 9
0x100421794  or      eax, 0FFFFFFFFh
0x100421797  mov     rbx, [rsp+58h+arg_10]
0x10042179c  add     rsp, 30h
0x1004217a0  pop     r15
0x1004217a2  pop     r14
0x1004217a4  pop     r13
0x1004217a6  pop     r12
0x1004217a8  pop     rsi
0x1004217a9  retn
0x1004217aa  test    ecx, ecx
0x1004217ac  js      short loc_1004217BD
0x1004217ae  cmp     esi, cs:_nhandle
0x1004217b4  jnb     short loc_1004217BD
0x1004217b6  mov     eax, 1
0x1004217bb  jmp     short loc_1004217BF
0x1004217bd  xor     eax, eax
0x1004217bf  test    eax, eax
0x1004217c1  jnz     short loc_1004217F6
0x1004217c3  mov     byte ptr [r9+38h], 1
0x1004217c8  and     dword ptr [r9+34h], 0
0x1004217cd  mov     byte ptr [r9+30h], 1
0x1004217d2  mov     dword ptr [r9+2Ch], 9
0x1004217da  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x1004217df  and     [rsp+58h+var_38], 0
0x1004217e5  xor     r9d, r9d; LineNo
0x1004217e8  xor     r8d, r8d; FileName
0x1004217eb  xor     edx, edx; FunctionName
0x1004217ed  xor     ecx, ecx; Expression
0x1004217ef  call    _invalid_parameter_internal
0x1004217f4  jmp     short loc_100421794
0x1004217f6  mov     rax, rsi
0x1004217f9  mov     r15, rsi
0x1004217fc  sar     r15, 6
0x100421800  lea     rcx, __pioinfo
0x100421807  and     eax, 3Fh
0x10042180a  lea     r12, [rax+rax*8]
0x10042180e  mov     rax, [rcx+r15*8]
0x100421812  test    byte ptr [rax+r12*8+38h], 1
0x100421818  jz      short loc_1004217C3
0x10042181a  mov     ecx, esi
0x10042181c  call    __acrt_lowio_lock_fh
0x100421821  or      r14d, 0FFFFFFFFh
0x100421825  lea     rax, __pioinfo
0x10042182c  mov     rax, [rax+r15*8]
0x100421830  test    byte ptr [rax+r12*8+38h], 1
0x100421836  jnz     short loc_10042184D
0x100421838  mov     byte ptr [rbx+30h], 1
0x10042183c  mov     dword ptr [rbx+2Ch], 9
0x100421843  mov     byte ptr [rbx+38h], 1
0x100421847  and     dword ptr [rbx+34h], 0
0x10042184b  jmp     short loc_100421862
0x10042184d  mov     r9, rbx
0x100421850  mov     r8d, r13d
0x100421853  mov     rdx, [rsp+58h+arg_8]
0x100421858  mov     ecx, esi
0x10042185a  call    _write_nolock
0x10042185f  mov     r14d, eax
0x100421862  mov     ecx, esi
0x100421864  call    __acrt_lowio_unlock_fh
0x100421869  mov     eax, r14d
0x10042186c  jmp     loc_100421797
0x1004254c6  push    rbp
0x1004254c8  sub     rsp, 30h
0x1004254cc  mov     rbp, rdx
0x1004254cf  mov     ecx, [rbp+60h]
0x1004254d2  add     rsp, 30h
0x1004254d6  pop     rbp
0x1004254d7  jmp     __acrt_lowio_unlock_fh
```
