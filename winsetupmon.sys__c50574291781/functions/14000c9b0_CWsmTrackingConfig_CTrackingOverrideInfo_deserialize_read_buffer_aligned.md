# CWsmTrackingConfig::CTrackingOverrideInfo::deserialize(read_buffer_aligned &)

- ea: `0x14000c9b0`
- end: `0x14000cac7`
- name: `?deserialize@CTrackingOverrideInfo@CWsmTrackingConfig@@UEAAJAEAVread_buffer_aligned@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(CWsmTrackingConfig::CTrackingOverrideInfo *__hidden this, struct read_buffer_aligned *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14000b358`
- `0x14000c9b0`
- `0x14000f9e0`
- `0x14000fa40`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingOverrideInfo::deserialize(
        __int64 **this,
        struct read_buffer_aligned *a2)
{
  __int64 result; // rax
  __int64 *v5; // rax
  __int64 *v6; // rcx
  __int64 *v7; // rax
  __int64 *v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // ecx
  int v14; // esi
  unsigned int v15; // esi

  CWsmTrackingConfig::CTrackingOverrideInfo::Release((CWsmTrackingConfig::CTrackingOverrideInfo *)this);
  result = ((__int64 (__fastcall *)(char *, struct read_buffer_aligned *))this[1][1])((char *)this + 8, a2);
  if ( (int)result >= 0 )
  {
    v5 = this[2];
    v6 = v5 ? (__int64 *)*v5 : 0LL;
    this[5] = v6;
    result = ((__int64 (__fastcall *)(char *, struct read_buffer_aligned *))this[3][1])((char *)this + 24, a2);
    if ( (int)result >= 0 )
    {
      v7 = this[4];
      if ( v7 )
        v8 = (__int64 *)*v7;
      else
        v8 = 0;
      this[6] = v8;
      v9 = *((_DWORD *)a2 + 3);
      if ( v9 == *((_DWORD *)a2 + 2) )
        return 2147483682LL;
      memmove(this + 7, (const void *)(*(_QWORD *)a2 + v9), 1u);
      v10 = ++*((_DWORD *)a2 + 3);
      if ( (v10 & 3) != 0 )
      {
        v11 = v10 + (*((_DWORD *)a2 + 3) & 3);
        v12 = 0xFFFFFFFFLL;
        if ( v11 >= v10 )
          v12 = v11;
        v13 = v11 < v10 ? 0xC0000095 : 0;
        if ( v11 < v10 )
          return v13;
        *((_DWORD *)a2 + 3) = v12;
      }
      else
      {
        v12 = *((unsigned int *)a2 + 3);
      }
      v14 = *((_DWORD *)a2 + 2);
      if ( (_DWORD)v12 != v14 )
      {
        v15 = v14 - v12;
        if ( v15 >= 4 )
          v15 = 4;
        memmove((char *)this + 60, (const void *)(*(_QWORD *)a2 + v12), v15);
        *((_DWORD *)a2 + 3) += v15;
        return 0;
      }
      return (unsigned int)-2147483614;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c9b0  mov     [rsp+arg_0], rbx
0x14000c9b5  mov     [rsp+arg_8], rsi
0x14000c9ba  push    rdi
0x14000c9bb  sub     rsp, 20h
0x14000c9bf  mov     rbx, rdx
0x14000c9c2  mov     rdi, rcx
0x14000c9c5  call    ?Release@CTrackingOverrideInfo@CWsmTrackingConfig@@IEAAXXZ; CWsmTrackingConfig::CTrackingOverrideInfo::Release(void)
0x14000c9ca  lea     rcx, [rdi+8]
0x14000c9ce  mov     rdx, rbx
0x14000c9d1  mov     rax, [rcx]
0x14000c9d4  mov     rax, [rax+8]
0x14000c9d8  call    _guard_dispatch_icall
0x14000c9dd  test    eax, eax
0x14000c9df  js      loc_14000CAB6
0x14000c9e5  mov     rax, [rdi+10h]
0x14000c9e9  test    rax, rax
0x14000c9ec  jz      short loc_14000C9F3
0x14000c9ee  mov     rcx, [rax]
0x14000c9f1  jmp     short loc_14000C9F5
0x14000c9f3  xor     ecx, ecx
0x14000c9f5  mov     [rdi+28h], rcx
0x14000c9f9  mov     rdx, rbx
0x14000c9fc  lea     rcx, [rdi+18h]
0x14000ca00  mov     rax, [rcx]
0x14000ca03  mov     rax, [rax+8]
0x14000ca07  call    _guard_dispatch_icall
0x14000ca0c  test    eax, eax
0x14000ca0e  js      loc_14000CAB6
0x14000ca14  mov     rax, [rdi+20h]
0x14000ca18  test    rax, rax
0x14000ca1b  jz      short loc_14000CA22
0x14000ca1d  mov     rcx, [rax]
0x14000ca20  jmp     short loc_14000CA24
0x14000ca22  xor     ecx, ecx
0x14000ca24  mov     [rdi+30h], rcx
0x14000ca28  mov     eax, [rbx+0Ch]
0x14000ca2b  mov     esi, [rbx+8]
0x14000ca2e  cmp     eax, esi
0x14000ca30  jz      short loc_14000CAB1
0x14000ca32  sub     esi, eax
0x14000ca34  mov     ecx, 1
0x14000ca39  cmp     esi, ecx
0x14000ca3b  mov     edx, eax
0x14000ca3d  cmovnb  esi, ecx
0x14000ca40  add     rdx, [rbx]; Src
0x14000ca43  mov     r8d, esi; Size
0x14000ca46  lea     rcx, [rdi+38h]; void *
0x14000ca4a  call    memmove
0x14000ca4f  add     [rbx+0Ch], esi
0x14000ca52  mov     r8d, [rbx+0Ch]
0x14000ca56  mov     eax, r8d
0x14000ca59  and     eax, 3
0x14000ca5c  jz      short loc_14000CA7C
0x14000ca5e  add     eax, r8d
0x14000ca61  or      edx, 0FFFFFFFFh
0x14000ca64  cmp     eax, r8d
0x14000ca67  cmovnb  edx, eax
0x14000ca6a  sbb     ecx, ecx
0x14000ca6c  and     ecx, 0C0000095h
0x14000ca72  cmp     eax, r8d
0x14000ca75  jb      short loc_14000CAAD
0x14000ca77  mov     [rbx+0Ch], edx
0x14000ca7a  jmp     short loc_14000CA7F
0x14000ca7c  mov     rdx, r8
0x14000ca7f  mov     esi, [rbx+8]
0x14000ca82  cmp     edx, esi
0x14000ca84  jz      short loc_14000CAA8
0x14000ca86  sub     esi, edx
0x14000ca88  lea     rcx, [rdi+3Ch]; void *
0x14000ca8c  mov     eax, 4
0x14000ca91  cmp     esi, eax
0x14000ca93  cmovnb  esi, eax
0x14000ca96  add     rdx, [rbx]; Src
0x14000ca99  mov     r8d, esi; Size
0x14000ca9c  call    memmove
0x14000caa1  add     [rbx+0Ch], esi
0x14000caa4  xor     eax, eax
0x14000caa6  jmp     short loc_14000CAB6
0x14000caa8  mov     ecx, 80000022h
0x14000caad  mov     eax, ecx
0x14000caaf  jmp     short loc_14000CAB6
0x14000cab1  mov     eax, 80000022h
0x14000cab6  mov     rbx, [rsp+28h+arg_0]
0x14000cabb  mov     rsi, [rsp+28h+arg_8]
0x14000cac0  add     rsp, 20h
0x14000cac4  pop     rdi
0x14000cac5  retn
```
