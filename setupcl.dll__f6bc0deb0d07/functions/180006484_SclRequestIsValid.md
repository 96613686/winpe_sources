# SclRequestIsValid

- ea: `0x180006484`
- end: `0x1800065f1`
- name: `SclRequestIsValid`
- size: `365`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002010`
- `0x180002640`
- `0x180005da0`
- `0x1800065f8`

## callees

- `0x180005938`
- `0x180006484`
- `0x18000de94`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18000653c`
- `ntdll!RtlValidSid` at `0x18000654f`
- `ntdll!RtlValidSid` at `0x18000653c`
- `ntdll!RtlValidSid` at `0x18000654f`

## pseudocode

```c
bool __fastcall SclRequestIsValid(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  bool v4; // bl
  __int16 v5; // r10
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // r11
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r11

  if ( !a2 || *(_DWORD *)a2 != (*(_DWORD *)a2 & 0x8000FF3F) )
    return 0;
  v4 = (unsigned __int8)SclOSIsValid(a1) != 0;
  if ( v3
    && *(_DWORD *)v3 == 2
    && ((v5 & 0x100) != 0 && !*(_QWORD *)(v3 + 24)
     || (v5 & 0x200) != 0 && !*(_QWORD *)(v3 + 32)
     || (v5 & 0x400) != 0 && !*(_QWORD *)(v3 + 40)
     || (v5 & 0x800) != 0 && !*(_QWORD *)(v3 + 48)
     || (v5 & 0x1000) != 0 && !*(_QWORD *)(v3 + 56)
     || (v5 & 0x2000) != 0 && (!*(_QWORD *)(v3 + 8) || !*(_QWORD *)(v3 + 48))
     || (v5 & 0x4000) != 0 && !*(_QWORD *)(v3 + 16)) )
  {
    v4 = 0;
  }
  if ( (v5 & 4) != 0
    && ((v6 = *(void **)(a2 + 8)) != 0 && !RtlValidSid(v6) || (v7 = *(void **)(a2 + 16)) != 0 && !RtlValidSid(v7)) )
  {
    v4 = 0;
  }
  v8 = 260;
  if ( (*(_DWORD *)a2 & 2) != 0
    && ((int)RtlStringCchLengthW(a2 + 24, 260, 0) < 0 || (int)RtlStringCchLengthW(a2 + 544, (unsigned int)v8, v9) < 0) )
  {
    v4 = 0;
  }
  if ( (*(_DWORD *)a2 & 8) != 0
    && ((int)RtlStringCchLengthW(a2 + 24, v8, 0) < 0 || (int)RtlStringCchLengthW(a2 + 544, v11, v10) < 0) )
  {
    v4 = 0;
  }
  if ( (*(_DWORD *)a2 & 0x10) != 0 && (int)RtlStringCchLengthW(a2 + 1072, 36, 0) < 0 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180006484  mov     [rsp+arg_0], rbx
0x180006489  push    rdi
0x18000648a  sub     rsp, 20h
0x18000648e  mov     rdi, rdx
0x180006491  test    rdx, rdx
0x180006494  jz      loc_1800065E4
0x18000649a  mov     r10d, [rdx]
0x18000649d  mov     eax, r10d
0x1800064a0  and     eax, 8000FF3Fh
0x1800064a5  cmp     r10d, eax
0x1800064a8  jnz     loc_1800065E4
0x1800064ae  call    SclOSIsValid
0x1800064b3  test    al, al
0x1800064b5  setnz   bl
0x1800064b8  test    rcx, rcx
0x1800064bb  jz      short loc_18000652D
0x1800064bd  cmp     dword ptr [rcx], 2
0x1800064c0  jnz     short loc_18000652D
0x1800064c2  bt      r10d, 8
0x1800064c7  jnb     short loc_1800064D0
0x1800064c9  cmp     qword ptr [rcx+18h], 0
0x1800064ce  jz      short loc_18000652B
0x1800064d0  bt      r10d, 9
0x1800064d5  jnb     short loc_1800064DE
0x1800064d7  cmp     qword ptr [rcx+20h], 0
0x1800064dc  jz      short loc_18000652B
0x1800064de  bt      r10d, 0Ah
0x1800064e3  jnb     short loc_1800064EC
0x1800064e5  cmp     qword ptr [rcx+28h], 0
0x1800064ea  jz      short loc_18000652B
0x1800064ec  bt      r10d, 0Bh
0x1800064f1  jnb     short loc_1800064FA
0x1800064f3  cmp     qword ptr [rcx+30h], 0
0x1800064f8  jz      short loc_18000652B
0x1800064fa  bt      r10d, 0Ch
0x1800064ff  jnb     short loc_180006508
0x180006501  cmp     qword ptr [rcx+38h], 0
0x180006506  jz      short loc_18000652B
0x180006508  bt      r10d, 0Dh
0x18000650d  jnb     short loc_18000651D
0x18000650f  cmp     qword ptr [rcx+8], 0
0x180006514  jz      short loc_18000652B
0x180006516  cmp     qword ptr [rcx+30h], 0
0x18000651b  jz      short loc_18000652B
0x18000651d  bt      r10d, 0Eh
0x180006522  jnb     short loc_18000652D
0x180006524  cmp     qword ptr [rcx+10h], 0
0x180006529  jnz     short loc_18000652D
0x18000652b  xor     bl, bl
0x18000652d  test    r10b, 4
0x180006531  jz      short loc_18000655B
0x180006533  mov     rcx, [rdi+8]; Sid
0x180006537  test    rcx, rcx
0x18000653a  jz      short loc_180006546
0x18000653c  call    cs:__imp_RtlValidSid
0x180006542  test    al, al
0x180006544  jz      short loc_180006559
0x180006546  mov     rcx, [rdi+10h]; Sid
0x18000654a  test    rcx, rcx
0x18000654d  jz      short loc_18000655B
0x18000654f  call    cs:__imp_RtlValidSid
0x180006555  test    al, al
0x180006557  jnz     short loc_18000655B
0x180006559  xor     bl, bl
0x18000655b  mov     eax, [rdi]
0x18000655d  mov     r11d, 104h
0x180006563  test    al, 2
0x180006565  jz      short loc_18000658F
0x180006567  lea     rcx, [rdi+18h]
0x18000656b  xor     r8d, r8d
0x18000656e  mov     edx, r11d
0x180006571  call    RtlStringCchLengthW
0x180006576  test    eax, eax
0x180006578  js      short loc_18000658D
0x18000657a  lea     rcx, [rdi+220h]
0x180006581  mov     edx, r11d
0x180006584  call    RtlStringCchLengthW
0x180006589  test    eax, eax
0x18000658b  jns     short loc_18000658F
0x18000658d  xor     bl, bl
0x18000658f  mov     eax, [rdi]
0x180006591  test    al, 8
0x180006593  jz      short loc_1800065BD
0x180006595  lea     rcx, [rdi+18h]
0x180006599  xor     r8d, r8d
0x18000659c  mov     rdx, r11
0x18000659f  call    RtlStringCchLengthW
0x1800065a4  test    eax, eax
0x1800065a6  js      short loc_1800065BB
0x1800065a8  lea     rcx, [rdi+220h]
0x1800065af  mov     rdx, r11
0x1800065b2  call    RtlStringCchLengthW
0x1800065b7  test    eax, eax
0x1800065b9  jns     short loc_1800065BD
0x1800065bb  xor     bl, bl
0x1800065bd  mov     eax, [rdi]
0x1800065bf  test    al, 10h
0x1800065c1  jz      short loc_1800065E0
0x1800065c3  xor     r8d, r8d
0x1800065c6  lea     rcx, [rdi+430h]
0x1800065cd  lea     edx, [r8+24h]
0x1800065d1  call    RtlStringCchLengthW
0x1800065d6  xor     ecx, ecx
0x1800065d8  movzx   ebx, bl
0x1800065db  test    eax, eax
0x1800065dd  cmovs   ebx, ecx
0x1800065e0  mov     al, bl
0x1800065e2  jmp     short loc_1800065E6
0x1800065e4  xor     al, al
0x1800065e6  mov     rbx, [rsp+28h+arg_0]
0x1800065eb  add     rsp, 20h
0x1800065ef  pop     rdi
0x1800065f0  retn
```
