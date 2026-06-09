# CDVRIndexObject::SetMmsID(_GUID const &)

- ea: `0x180004cb8`
- end: `0x180004d09`
- name: `?SetMmsID@CDVRIndexObject@@QEAAJAEBU_GUID@@@Z`
- size: `81`
- prototype: `__int64 __fastcall(CDVRIndexObject *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800039f0`
- `0x180004510`

## callees

- `0x180004cb8`

## pseudocode

```c
__int64 __fastcall CDVRIndexObject::SetMmsID(CDVRIndexObject *this, const struct _GUID *a2)
{
  __int128 v2; // xmm0
  _DWORD *v3; // rdx
  __int64 v5; // rdx
  _BYTE *v6; // rdx
  __int64 i; // rcx
  char v8; // al

  v2 = (__int128)*a2;
  v3 = (_DWORD *)*((_QWORD *)this + 24);
  *(_OWORD *)((char *)this + 56) = v2;
  *v3 = *((_DWORD *)this + 14);
  v5 = *((_QWORD *)this + 24);
  *(_WORD *)(v5 + 4) = *((_WORD *)this + 30);
  *(_WORD *)(v5 + 6) = *((_WORD *)this + 31);
  v6 = (_BYTE *)(*((_QWORD *)this + 24) + 8LL);
  for ( i = 0; i != 8; ++i )
  {
    v8 = *((_BYTE *)this + i + 64);
    *v6++ = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180004cb8  movups  xmm0, xmmword ptr [rdx]
0x180004cbb  mov     rdx, [rcx+0C0h]
0x180004cc2  mov     r8, rcx
0x180004cc5  movdqu  xmmword ptr [rcx+38h], xmm0
0x180004cca  mov     eax, [rcx+38h]
0x180004ccd  mov     [rdx], eax
0x180004ccf  mov     rdx, [rcx+0C0h]
0x180004cd6  movzx   eax, word ptr [rcx+3Ch]
0x180004cda  mov     [rdx+4], ax
0x180004cde  movzx   eax, word ptr [rcx+3Eh]
0x180004ce2  mov     [rdx+6], ax
0x180004ce6  mov     rdx, [rcx+0C0h]
0x180004ced  add     rdx, 8
0x180004cf1  xor     ecx, ecx
0x180004cf3  mov     al, [r8+rcx+40h]
0x180004cf8  inc     rcx
0x180004cfb  mov     [rdx], al
0x180004cfd  inc     rdx
0x180004d00  cmp     rcx, 8
0x180004d04  jnz     short loc_180004CF3
0x180004d06  xor     eax, eax
0x180004d08  retn
```
