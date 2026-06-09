# Tpm20ResourceMgr::ReplaceOutputHandle(bool,TpmBufferAccessor *,Tpm20Request const *)

- ea: `0x140007700`
- end: `0x140007845`
- name: `?ReplaceOutputHandle@Tpm20ResourceMgr@@AEAAJ_NPEAVTpmBufferAccessor@@PEBVTpm20Request@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(Tpm20ResourceMgr *__hidden this, bool, struct TpmBufferAccessor *, const struct Tpm20Request *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140016afc`

## callees

- `0x140007700`
- `0x14000784c`
- `0x1400078b8`

## pseudocode

```c
__int64 __fastcall Tpm20ResourceMgr::ReplaceOutputHandle(
        Tpm20ResourceMgr *this,
        char a2,
        struct TpmBufferAccessor *a3,
        const struct Tpm20Request *a4)
{
  unsigned int v5; // ecx
  __int64 v6; // r10
  __int64 v7; // rdi
  signed int i; // edx
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 **v12; // rdx
  __int64 *j; // rcx
  int v14; // r11d
  signed int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // rdx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  int v21; // [rsp+48h] [rbp+10h]

  v21 = 0;
  if ( !a2 )
    return 0;
  v5 = *((_DWORD *)a3 + 4) - *(_DWORD *)a3;
  if ( v5 + 4 < v5 || (v6 = v5, (unsigned __int64)v5 + 4 > *((unsigned int *)a3 + 2)) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v20 = 43;
LABEL_19:
      WPP_SF_(v19->AttachedDevice, v20, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
    }
  }
  else
  {
    v7 = *(_QWORD *)a3;
    for ( i = 0; (unsigned int)i < 4; ++i )
    {
      v9 = i;
      v10 = v6 - i;
      *((_BYTE *)&v21 + v9) = *(_BYTE *)(v10 + v7 + 3);
    }
    v11 = v21;
    v12 = (__int64 **)(*((_QWORD *)a4 + 2) + 8LL);
    for ( j = *v12; j != (__int64 *)v12; j = (__int64 *)*j )
    {
      if ( *((_DWORD *)j + 12) == v21 )
      {
        v14 = *((_DWORD *)j + 13);
        v15 = 0;
        v21 = v14;
        do
        {
          v16 = v15;
          v17 = v7 + 3 - v15++;
          *(_BYTE *)(v17 + v6) = *((_BYTE *)&v21 + v16);
        }
        while ( (unsigned int)v15 < 4 );
        *((_QWORD *)a3 + 2) += 4LL;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 45, a3, *((_QWORD *)a4 + 2), v11, v14);
        return 0;
      }
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v20 = 44;
      goto LABEL_19;
    }
  }
  return 3221225862LL;
}

```

## disassembly

```asm
0x140007700  mov     [rsp+arg_0], rbx
0x140007705  push    rdi
0x140007706  sub     rsp, 30h
0x14000770a  mov     [rsp+38h+arg_8], 0
0x140007712  mov     rbx, r9
0x140007715  test    dl, dl
0x140007717  jz      loc_1400077DB
0x14000771d  mov     ecx, [r8+10h]
0x140007721  sub     ecx, [r8]
0x140007724  lea     eax, [rcx+4]
0x140007727  cmp     eax, ecx
0x140007729  jb      loc_140007824
0x14000772f  mov     r10d, ecx
0x140007732  mov     ecx, [r8+8]
0x140007736  lea     rax, [r10+4]
0x14000773a  cmp     rax, rcx
0x14000773d  ja      loc_140007824
0x140007743  mov     rdi, [r8]
0x140007746  xor     edx, edx
0x140007748  movsxd  rcx, edx
0x14000774b  mov     rax, r10
0x14000774e  sub     rax, rcx
0x140007751  inc     edx
0x140007753  mov     al, [rax+rdi+3]
0x140007757  mov     byte ptr [rsp+rcx+38h+arg_8], al
0x14000775b  cmp     edx, 4
0x14000775e  jb      short loc_140007748
0x140007760  mov     rdx, [r9+10h]
0x140007764  mov     eax, [rsp+38h+arg_8]
0x140007768  add     rdx, 8
0x14000776c  mov     rcx, [rdx]
0x14000776f  cmp     rcx, rdx
0x140007772  jz      short loc_1400077EE
0x140007774  cmp     [rcx+30h], eax
0x140007777  jnz     short loc_1400077E9
0x140007779  mov     r11d, [rcx+34h]
0x14000777d  xor     r9d, r9d
0x140007780  mov     [rsp+38h+arg_8], r11d
0x140007785  movsxd  rcx, r9d
0x140007788  lea     rdx, [rdi+3]
0x14000778c  sub     rdx, rcx
0x14000778f  inc     r9d
0x140007792  mov     cl, byte ptr [rsp+rcx+38h+arg_8]
0x140007796  mov     [rdx+r10], cl
0x14000779a  cmp     r9d, 4
0x14000779e  jb      short loc_140007785
0x1400077a0  add     qword ptr [r8+10h], 4
0x1400077a5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400077ac  lea     rdx, WPP_GLOBAL_Control
0x1400077b3  cmp     rcx, rdx
0x1400077b6  jz      short loc_1400077DB
0x1400077b8  mov     edx, [rcx+2Ch]
0x1400077bb  test    dl, 4
0x1400077be  jz      short loc_1400077DB
0x1400077c0  mov     r9, [rbx+10h]
0x1400077c4  mov     edx, 2Dh ; '-'
0x1400077c9  mov     rcx, [rcx+18h]
0x1400077cd  mov     [rsp+38h+var_10], r11d
0x1400077d2  mov     [rsp+38h+var_18], eax
0x1400077d6  call    WPP_SF_qDD
0x1400077db  xor     eax, eax
0x1400077dd  mov     rbx, [rsp+38h+arg_0]
0x1400077e2  add     rsp, 30h
0x1400077e6  pop     rdi
0x1400077e7  retn
0x1400077e9  mov     rcx, [rcx]
0x1400077ec  jmp     short loc_14000776F
0x1400077ee  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400077f5  lea     rdx, WPP_GLOBAL_Control
0x1400077fc  cmp     rcx, rdx
0x1400077ff  jz      short loc_14000781D
0x140007801  mov     eax, [rcx+2Ch]
0x140007804  test    al, 1
0x140007806  jz      short loc_14000781D
0x140007808  mov     edx, 2Ch ; ','
0x14000780d  mov     rcx, [rcx+18h]
0x140007811  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140007818  call    WPP_SF_
0x14000781d  mov     eax, 0C0000186h
0x140007822  jmp     short loc_1400077DD
0x140007824  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000782b  lea     rdx, WPP_GLOBAL_Control
0x140007832  cmp     rcx, rdx
0x140007835  jz      short loc_14000781D
0x140007837  mov     eax, [rcx+2Ch]
0x14000783a  test    al, 1
0x14000783c  jz      short loc_14000781D
0x14000783e  mov     edx, 2Bh ; '+'
0x140007843  jmp     short loc_14000780D
```
