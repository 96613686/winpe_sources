# VerifyChunk(FileView const &)

- ea: `0x180009ab0`
- end: `0x180009c29`
- name: `?VerifyChunk@@YA_NAEBVFileView@@@Z`
- size: `377`
- prototype: `char __fastcall(const struct ChunkHeader **)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800098bc`
- `0x18000b8f4`
- `0x18007f4dc`
- `0x1800b4008`

## callees

- `0x180009ab0`
- `0x180009c30`
- `0x18000a180`
- `0x180092ee4`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180009b02`
- `ntdll!RtlComputeCrc32` at `0x180009b17`
- `ntdll!RtlComputeCrc32` at `0x180009b44`
- `ntdll!RtlComputeCrc32` at `0x180009b02`
- `ntdll!RtlComputeCrc32` at `0x180009b17`
- `ntdll!RtlComputeCrc32` at `0x180009b44`

## pseudocode

```c
char __fastcall VerifyChunk(const struct ChunkHeader **a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  const struct ChunkHeader *v4; // rbx
  ULONG v5; // eax
  ULONG v6; // eax
  const struct ChunkHeader *v7; // r8
  _QWORD *v9; // rcx
  __int64 v10; // rdx

  if ( !IsChunkHeaderValid(*a1) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return 0;
    }
    v10 = 18;
    goto LABEL_26;
  }
  if ( (unsigned int)(*(_DWORD *)(v3 + 48) - 512) > 0xFE00 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return 0;
    }
    v10 = 19;
    goto LABEL_26;
  }
  if ( (*(_BYTE *)(v3 + 120) & 4) != 0 || (unsigned __int8)AreAnyRestrictionsEnabled(2048, v2) )
    return 1;
  v4 = *a1;
  v5 = RtlComputeCrc32(0, (PUCHAR)*a1, 0x78u);
  v6 = RtlComputeCrc32(v5, (PUCHAR)v4 + 128, 0x180u);
  v7 = *a1;
  if ( v6 != *((_DWORD *)*a1 + 31) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return 0;
    }
    v10 = 20;
    goto LABEL_26;
  }
  if ( *((_QWORD *)v7 + 2) == -1
    || *((_DWORD *)*a1 + 13) == RtlComputeCrc32(0, (PUCHAR)a1[2] + 512, *((_DWORD *)v7 + 12) - 512) )
  {
    return 1;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v10 = 21;
LABEL_26:
    WPP_SF_(v9[2], v10, WPP_d678aa4655f1354a2fe0a66ad85eee91_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180009ab0  mov     [rsp+arg_0], rbx
0x180009ab5  push    rdi
0x180009ab6  sub     rsp, 20h
0x180009aba  mov     rdi, rcx
0x180009abd  mov     rcx, [rcx]; struct ChunkHeader *
0x180009ac0  call    ?IsChunkHeaderValid@@YA_NPEBUChunkHeader@@@Z; IsChunkHeaderValid(ChunkHeader const *)
0x180009ac5  test    al, al
0x180009ac7  jz      loc_180009B5F
0x180009acd  mov     eax, [rcx+30h]
0x180009ad0  sub     eax, 200h
0x180009ad5  cmp     eax, 0FE00h
0x180009ada  ja      loc_180009BE1
0x180009ae0  test    byte ptr [rcx+78h], 4
0x180009ae4  jnz     short loc_180009B52
0x180009ae6  mov     ecx, 800h
0x180009aeb  call    ?AreAnyRestrictionsEnabled@@YA_NW4FeatureRestrictions@@@Z; AreAnyRestrictionsEnabled(FeatureRestrictions)
0x180009af0  test    al, al
0x180009af2  jnz     short loc_180009B52
0x180009af4  mov     rbx, [rdi]
0x180009af7  mov     r8d, 78h ; 'x'; Length
0x180009afd  mov     rdx, rbx; Buffer
0x180009b00  xor     ecx, ecx; InitialCrc
0x180009b02  call    cs:__imp_RtlComputeCrc32
0x180009b08  lea     rdx, [rbx+80h]; Buffer
0x180009b0f  mov     r8d, 180h; Length
0x180009b15  mov     ecx, eax; InitialCrc
0x180009b17  call    cs:__imp_RtlComputeCrc32
0x180009b1d  mov     r8, [rdi]
0x180009b20  cmp     eax, [r8+7Ch]
0x180009b24  jnz     short loc_180009B8F
0x180009b26  cmp     qword ptr [r8+10h], 0FFFFFFFFFFFFFFFFh
0x180009b2b  jz      short loc_180009B52
0x180009b2d  mov     rax, [rdi+10h]
0x180009b31  xor     ecx, ecx; InitialCrc
0x180009b33  mov     r8d, [r8+30h]
0x180009b37  lea     rdx, [rax+200h]; Buffer
0x180009b3e  sub     r8d, edx
0x180009b41  add     r8d, eax; Length
0x180009b44  call    cs:__imp_RtlComputeCrc32
0x180009b4a  mov     rcx, [rdi]
0x180009b4d  cmp     [rcx+34h], eax
0x180009b50  jnz     short loc_180009BB8
0x180009b52  mov     al, 1
0x180009b54  mov     rbx, [rsp+28h+arg_0]
0x180009b59  add     rsp, 20h
0x180009b5d  pop     rdi
0x180009b5e  retn
0x180009b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b66  lea     rax, WPP_GLOBAL_Control
0x180009b6d  cmp     rcx, rax
0x180009b70  jnz     short loc_180009B76
0x180009b72  xor     al, al
0x180009b74  jmp     short loc_180009B54
0x180009b76  test    dword ptr [rcx+1Ch], 8000h
0x180009b7d  jz      short loc_180009B72
0x180009b7f  cmp     byte ptr [rcx+19h], 4
0x180009b83  jb      short loc_180009B72
0x180009b85  mov     edx, 12h
0x180009b8a  jmp     loc_180009C14
0x180009b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b96  lea     rax, WPP_GLOBAL_Control
0x180009b9d  cmp     rcx, rax
0x180009ba0  jz      short loc_180009B72
0x180009ba2  test    dword ptr [rcx+1Ch], 8000h
0x180009ba9  jz      short loc_180009B72
0x180009bab  cmp     byte ptr [rcx+19h], 4
0x180009baf  jb      short loc_180009B72
0x180009bb1  mov     edx, 14h
0x180009bb6  jmp     short loc_180009C14
0x180009bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bbf  lea     rax, WPP_GLOBAL_Control
0x180009bc6  cmp     rcx, rax
0x180009bc9  jz      short loc_180009B72
0x180009bcb  test    dword ptr [rcx+1Ch], 8000h
0x180009bd2  jz      short loc_180009B72
0x180009bd4  cmp     byte ptr [rcx+19h], 4
0x180009bd8  jb      short loc_180009B72
0x180009bda  mov     edx, 15h
0x180009bdf  jmp     short loc_180009C14
0x180009be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009be8  lea     rax, WPP_GLOBAL_Control
0x180009bef  cmp     rcx, rax
0x180009bf2  jz      loc_180009B72
0x180009bf8  test    dword ptr [rcx+1Ch], 8000h
0x180009bff  jz      loc_180009B72
0x180009c05  cmp     byte ptr [rcx+19h], 4
0x180009c09  jb      loc_180009B72
0x180009c0f  mov     edx, 13h
0x180009c14  mov     rcx, [rcx+10h]
0x180009c18  lea     r8, WPP_d678aa4655f1354a2fe0a66ad85eee91_Traceguids
0x180009c1f  call    WPP_SF_
0x180009c24  jmp     loc_180009B72
```
