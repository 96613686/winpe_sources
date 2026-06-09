# Tpm20ResourceMgr::GetInputObjects(TpmBufferAccessor *,Tpm20Request *)

- ea: `0x14000797c`
- end: `0x140007a8d`
- name: `?GetInputObjects@Tpm20ResourceMgr@@AEAAJPEAVTpmBufferAccessor@@PEAVTpm20Request@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(Tpm20ResourceMgr *__hidden this, struct TpmBufferAccessor *, struct Tpm20Request *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140016afc`

## callees

- `0x14000797c`
- `0x140009224`

## pseudocode

```c
__int64 __fastcall Tpm20ResourceMgr::GetInputObjects(
        Tpm20ResourceMgr *this,
        struct TpmBufferAccessor *a2,
        struct Tpm20Request *a3)
{
  __int64 v3; // rdi
  __int64 i; // rbx
  unsigned int v6; // ecx
  __int64 v7; // r11
  __int64 v8; // r10
  signed int j; // edx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 **v12; // r10
  __int64 *k; // rcx
  Tpm20ResourceMgr *v15; // [rsp+40h] [rbp+8h]

  v15 = this;
  v3 = *((_QWORD *)a2 + 2);
  LODWORD(v15) = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)a3 + 49) )
    {
      *((_QWORD *)a3 + 5) = v3;
      return 0;
    }
    v6 = *((_DWORD *)a2 + 4) - *(_DWORD *)a2;
    if ( v6 + 4 < v6 )
      return 2147483653LL;
    v7 = v6;
    if ( (unsigned __int64)v6 + 4 > *((unsigned int *)a2 + 2) )
      return 2147483653LL;
    v8 = *(_QWORD *)a2;
    for ( j = 0; (unsigned int)j < 4; ++j )
    {
      v10 = j;
      v11 = v8 + 3 - j;
      *((_BYTE *)&v15 + v10) = *(_BYTE *)(v11 + v7);
    }
    *((_QWORD *)a2 + 2) += 4LL;
    v12 = (__int64 **)*((_QWORD *)a3 + 2);
    if ( (unsigned int)v15 >> 24 == 2 || (unsigned int)v15 >> 24 == 3 || (unsigned int)v15 >> 24 == 128 )
      break;
    k = *v12;
LABEL_15:
    if ( !k )
      goto LABEL_17;
    *((_QWORD *)a3 + i + 6) = k;
  }
  for ( k = v12[1]; k != (__int64 *)(v12 + 1); k = (__int64 *)*k )
  {
    if ( *((_DWORD *)k + 13) == (_DWORD)v15 )
      goto LABEL_15;
  }
LABEL_17:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, v12, (_DWORD)v15);
  return 3222863905LL;
}

```

## disassembly

```asm
0x14000797c  mov     [rsp+arg_8], rbx
0x140007981  mov     [rsp+arg_0], rcx
0x140007986  push    rdi
0x140007987  sub     rsp, 30h
0x14000798b  mov     rdi, [rdx+10h]
0x14000798f  mov     r9, rdx
0x140007992  mov     dword ptr [rsp+38h+arg_0], 0
0x14000799a  xor     ebx, ebx
0x14000799c  cmp     ebx, [r8+0C4h]
0x1400079a3  jnb     short loc_140007A20
0x1400079a5  mov     ecx, [r9+10h]
0x1400079a9  sub     ecx, [r9]
0x1400079ac  lea     eax, [rcx+4]
0x1400079af  cmp     eax, ecx
0x1400079b1  jb      loc_140007A81
0x1400079b7  mov     r11d, ecx
0x1400079ba  mov     ecx, [r9+8]
0x1400079be  lea     rax, [r11+4]
0x1400079c2  cmp     rax, rcx
0x1400079c5  ja      loc_140007A81
0x1400079cb  mov     r10, [r9]
0x1400079ce  xor     edx, edx
0x1400079d0  movsxd  rcx, edx
0x1400079d3  lea     rax, [r10+3]
0x1400079d7  sub     rax, rcx
0x1400079da  inc     edx
0x1400079dc  mov     al, [rax+r11]
0x1400079e0  mov     byte ptr [rsp+rcx+38h+arg_0], al
0x1400079e4  cmp     edx, 4
0x1400079e7  jb      short loc_1400079D0
0x1400079e9  add     qword ptr [r9+10h], 4
0x1400079ee  mov     eax, dword ptr [rsp+38h+arg_0]
0x1400079f2  mov     edx, eax
0x1400079f4  mov     r10, [r8+10h]
0x1400079f8  shr     edx, 18h
0x1400079fb  sub     edx, 2
0x1400079fe  jz      short loc_140007A0A
0x140007a00  sub     edx, 1
0x140007a03  jz      short loc_140007A0A
0x140007a05  cmp     edx, 7Dh ; '}'
0x140007a08  jnz     short loc_140007A88
0x140007a0a  lea     rdx, [r10+8]
0x140007a0e  mov     rcx, [rdx]
0x140007a11  cmp     rcx, rdx
0x140007a14  jz      short loc_140007A43
0x140007a16  cmp     [rcx+34h], eax
0x140007a19  jz      short loc_140007A32
0x140007a1b  mov     rcx, [rcx]
0x140007a1e  jmp     short loc_140007A11
0x140007a20  mov     [r8+28h], rdi
0x140007a24  xor     eax, eax
0x140007a26  mov     rbx, [rsp+38h+arg_8]
0x140007a2b  add     rsp, 30h
0x140007a2f  pop     rdi
0x140007a30  retn
0x140007a32  test    rcx, rcx
0x140007a35  jz      short loc_140007A43
0x140007a37  mov     [r8+rbx*8+30h], rcx
0x140007a3c  inc     ebx
0x140007a3e  jmp     loc_14000799C
0x140007a43  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140007a4a  lea     rdx, WPP_GLOBAL_Control
0x140007a51  cmp     rcx, rdx
0x140007a54  jz      short loc_140007A7A
0x140007a56  mov     edx, [rcx+2Ch]
0x140007a59  test    dl, 2
0x140007a5c  jz      short loc_140007A7A
0x140007a5e  mov     rcx, [rcx+18h]
0x140007a62  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140007a69  mov     edx, 1Eh
0x140007a6e  mov     [rsp+38h+var_18], eax
0x140007a72  mov     r9, r10
0x140007a75  call    WPP_SF_qD
0x140007a7a  mov     eax, 0C0190021h
0x140007a7f  jmp     short loc_140007A26
0x140007a81  mov     eax, 80000005h
0x140007a86  jmp     short loc_140007A26
0x140007a88  mov     rcx, [r10]
0x140007a8b  jmp     short loc_140007A32
```
