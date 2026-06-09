# UdfSeqCacheGetPowInfo

- ea: `0x14001a3a4`
- end: `0x14001a471`
- name: `UdfSeqCacheGetPowInfo`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14001a234`
- `0x14001a478`

## callees

- `0x14001a3a4`
- `0x14002c7a0`
- `0x140037f1c`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheGetPowInfo(__int64 a1, int a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  __int64 v6; // rdi
  __int64 v8; // r8
  __int64 result; // rax

  v6 = a2;
  *a5 = 0;
  v8 = *(_QWORD *)(a1 + 8LL * a2 + 912);
  if ( !v8 )
    return 3221225626LL;
  if ( (*(_BYTE *)(a1 + 895) & 4) == 0
    && a2 == *(unsigned __int16 *)(a1 + 892)
    && (*(_BYTE *)(v8 + 4) & 2) != 0
    && *(_DWORD *)(v8 + 16) )
  {
    goto LABEL_12;
  }
  result = UdfSynchronizeDeviceCache(*(_QWORD *)(a1 + 24));
  if ( (int)result >= 0 )
  {
    *(_BYTE *)(a1 + 895) &= ~4u;
    result = UdfPowTrackInfoUpdate(a1);
    if ( (int)result >= 0 )
    {
      v8 = *(_QWORD *)(a1 + 8 * v6 + 912);
      if ( v8 && (*(_BYTE *)(v8 + 4) & 2) != 0 && *(_DWORD *)(v8 + 16) )
      {
        *(_WORD *)(a1 + 936) = 257;
        *(_BYTE *)(a1 + 938) = 1;
LABEL_12:
        *(_WORD *)(a1 + 892) = v6;
        *a4 = *(_DWORD *)(v8 + 16);
        result = 0;
        *a5 = v8;
        return result;
      }
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a3a4  push    rbx
0x14001a3a6  push    rsi
0x14001a3a7  push    rdi
0x14001a3a8  push    r14
0x14001a3aa  push    r15
0x14001a3ac  sub     rsp, 20h
0x14001a3b0  mov     r14, [rsp+48h+arg_20]
0x14001a3b5  mov     r15, r9
0x14001a3b8  movsxd  rdi, edx
0x14001a3bb  mov     rbx, rcx
0x14001a3be  mov     qword ptr [r14], 0
0x14001a3c5  mov     r8, [rcx+rdi*8+390h]
0x14001a3cd  test    r8, r8
0x14001a3d0  jz      loc_14001A45F
0x14001a3d6  test    byte ptr [rcx+37Fh], 4
0x14001a3dd  jnz     short loc_14001A3F8
0x14001a3df  movzx   eax, word ptr [rcx+37Ch]
0x14001a3e6  cmp     edi, eax
0x14001a3e8  jnz     short loc_14001A3F8
0x14001a3ea  test    byte ptr [r8+4], 2
0x14001a3ef  jz      short loc_14001A3F8
0x14001a3f1  cmp     dword ptr [r8+10h], 0
0x14001a3f6  jnz     short loc_14001A44A
0x14001a3f8  mov     rcx, [rcx+18h]
0x14001a3fc  call    UdfSynchronizeDeviceCache
0x14001a401  test    eax, eax
0x14001a403  js      short loc_14001A464
0x14001a405  and     byte ptr [rbx+37Fh], 0FBh
0x14001a40c  mov     rcx, rbx
0x14001a40f  call    UdfPowTrackInfoUpdate
0x14001a414  test    eax, eax
0x14001a416  js      short loc_14001A464
0x14001a418  mov     r8, [rbx+rdi*8+390h]
0x14001a420  test    r8, r8
0x14001a423  jz      short loc_14001A45F
0x14001a425  test    byte ptr [r8+4], 2
0x14001a42a  jz      short loc_14001A45F
0x14001a42c  cmp     dword ptr [r8+10h], 0
0x14001a431  jz      short loc_14001A45F
0x14001a433  mov     rax, 101010101010101h
0x14001a43d  mov     [rbx+3A8h], ax
0x14001a444  mov     [rbx+3AAh], al
0x14001a44a  mov     [rbx+37Ch], di
0x14001a451  mov     eax, [r8+10h]
0x14001a455  mov     [r15], eax
0x14001a458  xor     eax, eax
0x14001a45a  mov     [r14], r8
0x14001a45d  jmp     short loc_14001A464
0x14001a45f  mov     eax, 0C000009Ah
0x14001a464  add     rsp, 20h
0x14001a468  pop     r15
0x14001a46a  pop     r14
0x14001a46c  pop     rdi
0x14001a46d  pop     rsi
0x14001a46e  pop     rbx
0x14001a46f  retn
```
