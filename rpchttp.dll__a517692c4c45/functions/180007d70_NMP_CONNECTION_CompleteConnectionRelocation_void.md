# NMP_CONNECTION::CompleteConnectionRelocation(void)

- ea: `0x180007d70`
- end: `0x180007dc6`
- name: `?CompleteConnectionRelocation@NMP_CONNECTION@@UEAAXXZ`
- size: `86`
- prototype: `void __fastcall(NMP_CONNECTION *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007d70`

## pseudocode

```c
void __fastcall NMP_CONNECTION::CompleteConnectionRelocation(NMP_CONNECTION *this)
{
  __int64 v1; // rdx
  __int64 v2; // r8

  v1 = *((_QWORD *)this + 17) + 296LL;
  v2 = *(_QWORD *)v1;
  if ( *(_QWORD *)(*(_QWORD *)v1 + 8LL) != v1 )
    __fastfail(3u);
  *((_QWORD *)this + 21) = v1;
  *((_QWORD *)this + 20) = v2;
  *(_QWORD *)(v2 + 8) = (char *)this + 160;
  *(_QWORD *)v1 = (char *)this + 160;
  _InterlockedExchange(
    (volatile __int32 *)(*((_QWORD *)this + 17) + 120LL),
    ((*(_DWORD *)(*((_QWORD *)this + 17) + 120LL) - 0x10000000) & 0xF0000000) != 0
  ? *(_DWORD *)(*((_QWORD *)this + 17) + 120LL) - 0x10000000
  : 0);
}

```

## disassembly

```asm
0x180007d70  mov     rdx, [rcx+88h]
0x180007d77  add     rdx, 128h
0x180007d7e  mov     r8, [rdx]
0x180007d81  cmp     [r8+8], rdx
0x180007d85  jz      short loc_180007D8E
0x180007d87  mov     ecx, 3
0x180007d8c  int     29h; Win8: RtlFailFast(ecx)
0x180007d8e  lea     rax, [rcx+0A0h]
0x180007d95  mov     [rax+8], rdx
0x180007d99  mov     [rax], r8
0x180007d9c  mov     [r8+8], rax
0x180007da0  mov     [rdx], rax
0x180007da3  mov     r8, [rcx+88h]
0x180007daa  mov     edx, [r8+78h]
0x180007dae  add     edx, 0F0000000h
0x180007db4  mov     eax, edx
0x180007db6  and     eax, 0F0000000h
0x180007dbb  neg     eax
0x180007dbd  sbb     ecx, ecx
0x180007dbf  and     ecx, edx
0x180007dc1  xchg    ecx, [r8+78h]
0x180007dc5  retn
```
