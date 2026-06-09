# TSOctetStringToUnicodeGeneral(_UNICODE_STRING *,tagASN1octetstring_t const *,uchar)

- ea: `0x180009b2c`
- end: `0x180009bc8`
- name: `?TSOctetStringToUnicodeGeneral@@YAJPEAU_UNICODE_STRING@@PEBUtagASN1octetstring_t@@E@Z`
- size: `156`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, const struct tagASN1octetstring_t *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180018b28`
- `0x180018cf8`
- `0x180019958`
- `0x18001a914`

## callees

- `0x180005ed0`
- `0x180006530`
- `0x180007df0`
- `0x180009b2c`
- `0x1800182c8`

## pseudocode

```c
__int64 __fastcall TSOctetStringToUnicodeGeneral(struct _UNICODE_STRING *a1, const struct tagASN1octetstring_t *a2)
{
  int v3; // edi
  unsigned __int8 v4; // r8
  __int64 v5; // r9
  char v6; // r10
  int v7; // eax
  PWSTR Buffer; // rcx
  struct _UNICODE_STRING v10; // [rsp+20h] [rbp-18h] BYREF

  v10 = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  *a1 = 0;
  v3 = RtlULongToUShort(*(_DWORD *)a2, &v10.Length);
  if ( v3 < 0
    || ((v10.Buffer = *(PWSTR *)(v5 + 8), v10.MaximumLength = v10.Length, v6)
      ? (v7 = TSDuplicatePassword(a1, &v10))
      : (v7 = TSDuplicateStringEx(a1, &v10, v4)),
        v3 = v7,
        v7 < 0) )
  {
    Buffer = a1->Buffer;
    if ( Buffer )
    {
      TSFree(Buffer);
      a1->Buffer = 0;
      a1->Length = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009b2c  mov     [rsp+arg_0], rbx
0x180009b31  push    rdi
0x180009b32  sub     rsp, 30h
0x180009b36  xorps   xmm0, xmm0
0x180009b39  mov     r10b, r8b
0x180009b3c  mov     r9, rdx
0x180009b3f  mov     rbx, rcx
0x180009b42  movups  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x180009b47  test    rcx, rcx
0x180009b4a  jz      short loc_180009BB8
0x180009b4c  test    rdx, rdx
0x180009b4f  jz      short loc_180009BB8
0x180009b51  movups  xmmword ptr [rcx], xmm0
0x180009b54  mov     ecx, [r9]; unsigned int
0x180009b57  lea     rdx, [rsp+38h+var_18]; unsigned __int16 *
0x180009b5c  call    ?RtlULongToUShort@@YAJKPEAG@Z; RtlULongToUShort(ulong,ushort *)
0x180009b61  mov     edi, eax
0x180009b63  test    eax, eax
0x180009b65  js      short loc_180009B99
0x180009b67  mov     rax, [r9+8]
0x180009b6b  lea     rdx, [rsp+38h+var_18]; struct _UNICODE_STRING *
0x180009b70  mov     [rsp+38h+var_18.Buffer], rax
0x180009b75  mov     rcx, rbx; struct _UNICODE_STRING *
0x180009b78  movzx   eax, [rsp+38h+var_18.Length]
0x180009b7d  mov     [rsp+38h+var_18.MaximumLength], ax
0x180009b82  test    r10b, r10b
0x180009b85  jnz     short loc_180009B8E
0x180009b87  call    ?TSDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; TSDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180009b8c  jmp     short loc_180009B93
0x180009b8e  call    ?TSDuplicatePassword@@YAJPEAU_UNICODE_STRING@@0@Z; TSDuplicatePassword(_UNICODE_STRING *,_UNICODE_STRING *)
0x180009b93  mov     edi, eax
0x180009b95  test    eax, eax
0x180009b97  jns     short loc_180009BB4
0x180009b99  mov     rcx, [rbx+8]; void *
0x180009b9d  test    rcx, rcx
0x180009ba0  jz      short loc_180009BB4
0x180009ba2  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180009ba7  xor     eax, eax
0x180009ba9  mov     qword ptr [rbx+8], 0
0x180009bb1  mov     [rbx], ax
0x180009bb4  mov     eax, edi
0x180009bb6  jmp     short loc_180009BBD
0x180009bb8  mov     eax, 0C000000Dh
0x180009bbd  mov     rbx, [rsp+38h+arg_0]
0x180009bc2  add     rsp, 30h
0x180009bc6  pop     rdi
0x180009bc7  retn
```
