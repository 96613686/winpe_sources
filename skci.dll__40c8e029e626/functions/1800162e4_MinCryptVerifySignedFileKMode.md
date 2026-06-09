# MinCryptVerifySignedFileKMode

- ea: `0x1800162e4`
- end: `0x1800163b6`
- name: `MinCryptVerifySignedFileKMode`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800458d8`
- `0x180045a08`

## callees

- `0x180015624`
- `0x1800162e4`
- `0x180033980`
- `0x18004cd54`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x180016370`
- `securekernel!RtlCompareMemory` at `0x180016370`

## pseudocode

```c
__int64 __fastcall MinCryptVerifySignedFileKMode(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        _OWORD *a6)
{
  __int64 *v7; // rcx
  __int64 result; // rax
  char v10[8]; // [rsp+50h] [rbp-68h] BYREF
  void *Source2; // [rsp+58h] [rbp-60h]
  _BYTE v12[64]; // [rsp+60h] [rbp-58h] BYREF

  v7 = qword_180052CF0;
  if ( a2 )
    v7 = a2;
  result = MinCrypK_VerifySignedDataKModeEx(*(_QWORD *)a1, *(_DWORD *)(a1 + 8), 0, 0, (__int64)v7, a3, v10, a5, a6);
  if ( (int)result >= 0 )
  {
    if ( *(_DWORD *)v10 == 10
      && RtlCompareMemory(qword_1800521A8, Source2, 0xAu) == 10
      && (int)MinAsn1ParseIndirectData(v12, a4) >= 0 )
    {
      return 0;
    }
    else
    {
      return 3221226536LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800162e4  push    rbx
0x1800162e6  sub     rsp, 0B0h
0x1800162ed  mov     rax, cs:__security_cookie
0x1800162f4  xor     rax, rsp
0x1800162f7  mov     [rsp+0B8h+var_18], rax
0x1800162ff  mov     rax, [rsp+0B8h+arg_28]
0x180016307  mov     r10, rcx
0x18001630a  mov     [rsp+0B8h+var_78], rax; __int64
0x18001630f  lea     rcx, qword_180052CF0
0x180016316  mov     rbx, r9
0x180016319  lea     rax, [rsp+0B8h+var_68]
0x18001631e  mov     r9, [rsp+0B8h+arg_20]
0x180016326  test    rdx, rdx
0x180016329  mov     [rsp+0B8h+var_80], r9; __int64
0x18001632e  cmovnz  rcx, rdx
0x180016332  mov     [rsp+0B8h+var_88], rax; void *
0x180016337  mov     edx, [r10+8]; int
0x18001633b  xor     r9d, r9d; int
0x18001633e  mov     qword ptr [rsp+0B8h+var_90], r8; int
0x180016343  xor     r8d, r8d; int
0x180016346  mov     [rsp+0B8h+var_98], rcx; __int64
0x18001634b  mov     rcx, [r10]; int
0x18001634e  call    MinCrypK_VerifySignedDataKModeEx
0x180016353  test    eax, eax
0x180016355  js      short loc_18001639C
0x180016357  cmp     dword ptr [rsp+0B8h+var_68], 0Ah
0x18001635c  jnz     short loc_180016397
0x18001635e  mov     rdx, [rsp+0B8h+Source2]; Source2
0x180016363  lea     rcx, qword_1800521A8; Source1
0x18001636a  mov     r8d, 0Ah; Length
0x180016370  call    cs:__imp_RtlCompareMemory
0x180016377  nop     dword ptr [rax+rax+00h]
0x18001637c  cmp     rax, 0Ah
0x180016380  jnz     short loc_180016397
0x180016382  mov     rdx, rbx
0x180016385  lea     rcx, [rsp+0B8h+var_58]
0x18001638a  call    MinAsn1ParseIndirectData
0x18001638f  test    eax, eax
0x180016391  js      short loc_180016397
0x180016393  xor     eax, eax
0x180016395  jmp     short loc_18001639C
0x180016397  mov     eax, 0C0000428h
0x18001639c  mov     rcx, [rsp+0B8h+var_18]
0x1800163a4  xor     rcx, rsp; StackCookie
0x1800163a7  call    __security_check_cookie
0x1800163ac  add     rsp, 0B0h
0x1800163b3  pop     rbx
0x1800163b4  retn
```
