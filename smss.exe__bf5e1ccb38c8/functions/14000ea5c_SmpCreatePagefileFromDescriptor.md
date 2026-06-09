# SmpCreatePagefileFromDescriptor

- ea: `0x14000ea5c`
- end: `0x14000eae3`
- name: `SmpCreatePagefileFromDescriptor`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b464`

## callees

- `0x14000ea5c`
- `0x14000f6f4`

## pseudocode

```c
__int64 __fastcall SmpCreatePagefileFromDescriptor(__int64 a1, int a2)
{
  __int64 *v2; // rbx
  int PagefileOnVolume; // r8d
  __int64 v6; // rdx
  bool v7; // zf

  v2 = (__int64 *)SmpVolumeDescriptorList;
  PagefileOnVolume = -1073741772;
  while ( v2 != &SmpVolumeDescriptorList )
  {
    v6 = (__int64)v2;
    v2 = (__int64 *)*v2;
    if ( (*(_BYTE *)(a1 + 92) & 4) != 0 )
    {
      if ( (*(_BYTE *)(v6 + 16) & 0x12) == 0 )
      {
        v7 = (*(_DWORD *)(v6 + 24) & 0x40000) == 0 || (*(_BYTE *)(v6 + 16) & 1) != 0;
        goto LABEL_7;
      }
    }
    else
    {
      v7 = *(_WORD *)(v6 + 28) == *(_WORD *)(*(_QWORD *)(a1 + 24) + 8LL);
LABEL_7:
      if ( v7 )
      {
        PagefileOnVolume = SmpCreatePagefileOnVolume(a1, v6, a2);
        if ( PagefileOnVolume >= 0 )
          return (unsigned int)PagefileOnVolume;
      }
    }
  }
  return (unsigned int)PagefileOnVolume;
}

```

## disassembly

```asm
0x14000ea5c  mov     [rsp+arg_0], rbx
0x14000ea61  mov     [rsp+arg_8], rsi
0x14000ea66  push    rdi
0x14000ea67  sub     rsp, 20h
0x14000ea6b  mov     rbx, cs:SmpVolumeDescriptorList
0x14000ea72  mov     esi, edx
0x14000ea74  mov     rdi, rcx
0x14000ea77  mov     r8d, 0C0000034h
0x14000ea7d  lea     rax, SmpVolumeDescriptorList
0x14000ea84  cmp     rbx, rax
0x14000ea87  jz      short loc_14000EAD0
0x14000ea89  test    byte ptr [rdi+5Ch], 4
0x14000ea8d  mov     rdx, rbx
0x14000ea90  mov     rbx, [rbx]
0x14000ea93  jz      short loc_14000EAB0
0x14000ea95  test    byte ptr [rdx+10h], 12h
0x14000ea99  jnz     short loc_14000EA7D
0x14000ea9b  test    dword ptr [rdx+18h], 40000h
0x14000eaa2  setnz   cl
0x14000eaa5  test    byte ptr [rdx+10h], 1
0x14000eaa9  setz    al
0x14000eaac  test    al, cl
0x14000eaae  jmp     short loc_14000EABC
0x14000eab0  mov     rax, [rdi+18h]
0x14000eab4  movzx   ecx, word ptr [rax+8]
0x14000eab8  cmp     [rdx+1Ch], cx
0x14000eabc  jnz     short loc_14000EA7D
0x14000eabe  mov     r8d, esi
0x14000eac1  mov     rcx, rdi
0x14000eac4  call    SmpCreatePagefileOnVolume
0x14000eac9  mov     r8d, eax
0x14000eacc  test    eax, eax
0x14000eace  js      short loc_14000EA7D
0x14000ead0  mov     rbx, [rsp+28h+arg_0]
0x14000ead5  mov     eax, r8d
0x14000ead8  mov     rsi, [rsp+28h+arg_8]
0x14000eadd  add     rsp, 20h
0x14000eae1  pop     rdi
0x14000eae2  retn
```
