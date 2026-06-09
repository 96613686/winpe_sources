# ContextCreateChal

- ea: `0x18001ad3c`
- end: `0x18001b2f2`
- name: `ContextCreateChal`
- size: `1462`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18001e4b0`

## callees

- `0x1800061a0`
- `0x180006de0`
- `0x180009770`
- `0x18000c4c0`
- `0x180011fec`
- `0x180012c5c`
- `0x1800185b8`
- `0x180018b18`
- `0x18001ad3c`
- `0x18002232c`
- `0x180029c98`
- `0x1800377bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001afb1`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001afcb`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001b131`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001b15d`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001b1b1`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001afb1`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001afcb`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001b131`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001b15d`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18001b1b1`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x18001b182`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x18001b182`
- `ntdll!RtlReleaseResource` at `0x18001af39`
- `ntdll!RtlReleaseResource` at `0x18001af39`
- `ntdll!RtlAcquireResourceShared` at `0x18001aeed`
- `ntdll!RtlAcquireResourceShared` at `0x18001aeed`

## pseudocode

```c
__int64 __fastcall ContextCreateChal(__int64 a1, __int128 *a2, __int64 a3)
{
  unsigned int v6; // ebx
  char *Memory; // rdi
  char *v8; // rax
  char *v9; // rsi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r8
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int128 *v22; // r9
  const char *v23; // r8
  __int64 v24; // rax
  size_t v25; // r14
  __int64 v26; // rax
  __int128 v28; // [rsp+30h] [rbp-28h] BYREF
  char *Source[2]; // [rsp+40h] [rbp-18h] BYREF
  int v30; // [rsp+B8h] [rbp+60h]

  v28 = 0;
  *(_OWORD *)Source = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
  v6 = 0;
  Memory = (char *)DigestAllocateMemory(0x3001u);
  if ( !Memory )
  {
    v6 = -2146893056;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
    goto LABEL_83;
  }
  v8 = (char *)DigestAllocateMemory(0x1001u);
  v9 = v8;
  if ( !v8 )
  {
    v6 = -2146893056;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 184;
LABEL_80:
      WPP_SF_(v10[2], v11, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  *Memory = 0;
  *v8 = 0;
  if ( !a1 || !a3 || !a2 )
  {
    v6 = -1073741811;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 185;
      goto LABEL_80;
    }
    goto LABEL_81;
  }
  v12 = *(_QWORD *)(a1 + 624);
  if ( v12 )
    v6 = SsiIGetRealmDirectives(v12, Source);
  v13 = LOWORD(Source[0])
      + *(unsigned __int16 *)(a1 + 64)
      + *(unsigned __int16 *)(a1 + 112)
      + 400
      + 2
      * ((unsigned __int16)g_strNtDigestUTF8ServerRealm
       + (unsigned __int16)g_strNTDigestISO8859ServerRealm
       + (unsigned int)*(unsigned __int16 *)a2);
  if ( (unsigned int)v13 > 0x800 )
  {
    v6 = -1073741789;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v13);
    goto LABEL_81;
  }
  v30 = *(_DWORD *)(a1 + 44);
  if ( *(_DWORD *)(a1 + 48) == 4 )
  {
    RtlAcquireResourceShared(&g_RtlResource_CipherList, 1u);
    v14 = "md5-sess";
    if ( v30 != 4 )
      v14 = "MD5-sess";
    sprintf_s(
      Memory,
      0x3001u,
      "qop=\"auth,auth-int,auth-conf\",cipher=\"%s\",algorithm=%s,nonce=\"%hZ\"",
      g_strParameter_CipherList.Buffer,
      v14,
      a1 + 64,
      v28);
    RtlReleaseResource(&g_RtlResource_CipherList);
  }
  else
  {
    v15 = "md5-sess";
    v16 = "qop=\"auth,auth-int\",algorithm=%s,nonce=\"%hZ\"";
    if ( *(_DWORD *)(a1 + 48) != 3 )
      v16 = "qop=\"auth\",algorithm=%s,nonce=\"%hZ\"";
    if ( *(_DWORD *)(a1 + 44) != 4 )
      v15 = "MD5-sess";
    sprintf_s(Memory, 0x3001u, v16, v15, a1 + 64);
  }
  if ( *(_WORD *)(a1 + 112) && *(_DWORD *)(a1 + 44) != 4 )
  {
    sprintf_s(v9, 0x1001u, ",opaque=\"%hZ\"");
    _o_strcat_s(Memory, 12289, v9);
  }
  if ( *(_DWORD *)(a1 + 60) == 2 )
    _o_strcat_s(Memory, 12289, ",charset=utf-8");
  if ( *((_QWORD *)a2 + 1) )
  {
    if ( *(_WORD *)a2 )
    {
      v17 = BackslashEncodeString(a2, &v28);
      v6 = v17;
      if ( v17 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_81;
        v19 = 187;
        goto LABEL_41;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_57;
      v21 = 188;
      v22 = a2;
LABEL_56:
      WPP_SF_aZaZ(v20[2], v21, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v22, &v28);
LABEL_57:
      sprintf_s(v9, 0x1001u, ",realm=\"%hZ\"", &v28);
      _o_strcat_s(Memory, 12289, v9);
      goto LABEL_60;
    }
    v23 = ",realm=\"\"";
  }
  else
  {
    if ( v30 == 4 && *(_DWORD *)(a1 + 60) == 2 )
    {
      if ( !(_WORD)g_strNtDigestUTF8ServerRealm )
        goto LABEL_60;
      v17 = BackslashEncodeString(&g_strNtDigestUTF8ServerRealm, &v28);
      v6 = v17;
      if ( v17 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_81;
        v19 = 189;
LABEL_41:
        WPP_SF_d(v18[2], v19, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, (unsigned int)v17);
        goto LABEL_81;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_57;
      v21 = 190;
      v22 = &g_strNtDigestUTF8ServerRealm;
      goto LABEL_56;
    }
    sprintf_s(v9, 0x1001u, ",realm=\"%s\"", "Digest");
    v23 = v9;
  }
  _o_strcat_s(Memory, 12289, v23);
LABEL_60:
  if ( LOWORD(Source[0]) )
    strncat_s(Memory, 0x3001u, Source[1], LOWORD(Source[0]));
  if ( (*(_DWORD *)(a1 + 36) & 0x200000) != 0 )
  {
    sprintf_s(v9, 0x1001u, ",stale=true");
    _o_strcat_s(Memory, 12289, v9);
  }
  v24 = -1;
  do
    ++v24;
  while ( Memory[v24] );
  v25 = (unsigned __int16)v24;
  if ( *(_DWORD *)a3 )
  {
    if ( (unsigned int)(unsigned __int16)v24 > *(_DWORD *)a3 )
    {
      v6 = -1073741789;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          194,
          &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
          (unsigned __int16)v24,
          *(_DWORD *)a3);
      goto LABEL_81;
    }
    goto LABEL_72;
  }
  v26 = DigestAllocateMemory((unsigned __int16)v24);
  *(_QWORD *)(a3 + 8) = v26;
  if ( v26 )
  {
    *(_DWORD *)(a3 + 4) = 1;
LABEL_72:
    memcpy_0(*(void **)(a3 + 8), Memory, v25);
    *(_DWORD *)a3 = v25;
    goto LABEL_81;
  }
  v6 = -2146893056;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 193;
    goto LABEL_80;
  }
LABEL_81:
  DigestFreeMemory(Memory);
  if ( v9 )
    DigestFreeMemory(v9);
LABEL_83:
  StringFree(&v28);
  StringFree(Source);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18001ad3c  push    rbp
0x18001ad3e  push    rbx
0x18001ad3f  push    rsi
0x18001ad40  push    rdi
0x18001ad41  push    r12
0x18001ad43  push    r13
0x18001ad45  push    r14
0x18001ad47  push    r15
0x18001ad49  mov     rbp, rsp
0x18001ad4c  sub     rsp, 58h
0x18001ad50  xorps   xmm0, xmm0
0x18001ad53  xorps   xmm1, xmm1
0x18001ad56  movups  [rbp+var_28], xmm0
0x18001ad5a  mov     r12, r8
0x18001ad5d  mov     r15, rdx
0x18001ad60  movups  xmmword ptr [rbp+Source], xmm1
0x18001ad64  mov     r14, rcx
0x18001ad67  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad6e  lea     r13, WPP_GLOBAL_Control
0x18001ad75  cmp     rcx, r13
0x18001ad78  jz      short loc_18001AD95
0x18001ad7a  test    byte ptr [rcx+1Ch], 80h
0x18001ad7e  jz      short loc_18001AD95
0x18001ad80  mov     rcx, [rcx+10h]
0x18001ad84  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001ad8b  mov     edx, 0B6h
0x18001ad90  call    WPP_SF_
0x18001ad95  mov     ecx, 3001h; Size
0x18001ad9a  call    DigestAllocateMemory
0x18001ad9f  xor     ebx, ebx
0x18001ada1  mov     rdi, rax
0x18001ada4  test    rax, rax
0x18001ada7  jnz     short loc_18001ADE2
0x18001ada9  mov     ebx, 80090300h
0x18001adae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adb5  cmp     rcx, r13
0x18001adb8  jz      loc_18001B2A3
0x18001adbe  test    byte ptr [rcx+1Ch], 1
0x18001adc2  jz      loc_18001B2A3
0x18001adc8  mov     rcx, [rcx+10h]
0x18001adcc  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001add3  mov     edx, 0B7h
0x18001add8  call    WPP_SF_
0x18001addd  jmp     loc_18001B2A3
0x18001ade2  mov     ecx, 1001h; Size
0x18001ade7  call    DigestAllocateMemory
0x18001adec  mov     rsi, rax
0x18001adef  test    rax, rax
0x18001adf2  jnz     short loc_18001AE1D
0x18001adf4  mov     ebx, 80090300h
0x18001adf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae00  cmp     rcx, r13
0x18001ae03  jz      loc_18001B28E
0x18001ae09  test    byte ptr [rcx+1Ch], 1
0x18001ae0d  jz      loc_18001B28E
0x18001ae13  mov     edx, 0B8h
0x18001ae18  jmp     loc_18001B27E
0x18001ae1d  mov     [rdi], bl
0x18001ae1f  mov     [rax], bl
0x18001ae21  test    r14, r14
0x18001ae24  jz      loc_18001B262
0x18001ae2a  test    r12, r12
0x18001ae2d  jz      loc_18001B262
0x18001ae33  test    r15, r15
0x18001ae36  jz      loc_18001B262
0x18001ae3c  mov     rcx, [r14+270h]
0x18001ae43  test    rcx, rcx
0x18001ae46  jz      short loc_18001AE53
0x18001ae48  lea     rdx, [rbp+Source]
0x18001ae4c  call    SsiIGetRealmDirectives
0x18001ae51  mov     ebx, eax
0x18001ae53  movzx   ecx, word ptr cs:g_strNTDigestISO8859ServerRealm
0x18001ae5a  lea     r13, [r14+40h]
0x18001ae5e  movzx   r9d, word ptr [r15]
0x18001ae62  movzx   eax, word ptr [rbp+Source]
0x18001ae66  add     r9d, ecx
0x18001ae69  movzx   ecx, word ptr cs:g_strNtDigestUTF8ServerRealm
0x18001ae70  add     r9d, ecx
0x18001ae73  movzx   ecx, word ptr [r14+70h]
0x18001ae78  add     ecx, 190h
0x18001ae7e  lea     r9d, [rcx+r9*2]
0x18001ae82  movzx   ecx, word ptr [r13+0]
0x18001ae87  add     r9d, ecx
0x18001ae8a  add     r9d, eax
0x18001ae8d  cmp     r9d, 800h
0x18001ae94  jbe     short loc_18001AED6
0x18001ae96  mov     ebx, 0C0000023h
0x18001ae9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aea2  lea     r13, WPP_GLOBAL_Control
0x18001aea9  cmp     rcx, r13
0x18001aeac  jz      loc_18001B28E
0x18001aeb2  test    byte ptr [rcx+1Ch], 1
0x18001aeb6  jz      loc_18001B28E
0x18001aebc  mov     rcx, [rcx+10h]
0x18001aec0  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001aec7  mov     edx, 0BAh
0x18001aecc  call    WPP_SF_d
0x18001aed1  jmp     loc_18001B28E
0x18001aed6  cmp     dword ptr [r14+30h], 4
0x18001aedb  mov     ecx, [r14+2Ch]
0x18001aedf  mov     [rbp+arg_18], ecx
0x18001aee2  jnz     short loc_18001AF41
0x18001aee4  mov     dl, 1; Wait
0x18001aee6  lea     rcx, g_RtlResource_CipherList; Resource
0x18001aeed  call    cs:__imp_RtlAcquireResourceShared
0x18001aef3  cmp     [rbp+arg_18], 4
0x18001aef7  lea     rax, String1; "MD5-sess"
0x18001aefe  mov     [rsp+58h+var_30], r13
0x18001af03  lea     r9, aMd5Sess_0; "md5-sess"
0x18001af0a  cmovnz  r9, rax
0x18001af0e  lea     r8, aQopAuthAuthInt; "qop=\"auth,auth-int,auth-conf\",cipher="...
0x18001af15  mov     [rsp+58h+var_38], r9
0x18001af1a  mov     r13d, 3001h
0x18001af20  mov     r9, cs:g_strParameter_CipherList.Buffer
0x18001af27  mov     edx, r13d; BufferCount
0x18001af2a  mov     rcx, rdi; Buffer
0x18001af2d  call    sprintf_s
0x18001af32  lea     rcx, g_RtlResource_CipherList; Resource
0x18001af39  call    cs:__imp_RtlReleaseResource
0x18001af3f  jmp     short loc_18001AF81
0x18001af41  cmp     dword ptr [r14+30h], 3
0x18001af46  lea     rax, String1; "MD5-sess"
0x18001af4d  mov     [rsp+58h+var_38], r13
0x18001af52  lea     r9, aMd5Sess_0; "md5-sess"
0x18001af59  mov     r13d, 3001h
0x18001af5f  lea     r8, aQopAuthAuthInt_0; "qop=\"auth,auth-int\",algorithm=%s,nonc"...
0x18001af66  mov     edx, r13d; BufferCount
0x18001af69  jz      short loc_18001AF72
0x18001af6b  lea     r8, aQopAuthAlgorit; "qop=\"auth\",algorithm=%s,nonce=\"%hZ\""
0x18001af72  cmp     ecx, 4
0x18001af75  mov     rcx, rdi; Buffer
0x18001af78  cmovnz  r9, rax
0x18001af7c  call    sprintf_s
0x18001af81  lea     r9, [r14+70h]
0x18001af85  xor     eax, eax
0x18001af87  cmp     [r9], ax
0x18001af8b  jz      short loc_18001AFB7
0x18001af8d  cmp     dword ptr [r14+2Ch], 4
0x18001af92  jz      short loc_18001AFB7
0x18001af94  lea     r8, aOpaqueHz; ",opaque=\"%hZ\""
0x18001af9b  mov     edx, 1001h; BufferCount
0x18001afa0  mov     rcx, rsi; Buffer
0x18001afa3  call    sprintf_s
0x18001afa8  mov     r8, rsi
0x18001afab  mov     rdx, r13
0x18001afae  mov     rcx, rdi
0x18001afb1  call    cs:__imp__o_strcat_s
0x18001afb7  cmp     dword ptr [r14+3Ch], 2
0x18001afbc  jnz     short loc_18001AFD1
0x18001afbe  lea     r8, aCharsetUtf8; ",charset=utf-8"
0x18001afc5  mov     rdx, r13
0x18001afc8  mov     rcx, rdi
0x18001afcb  call    cs:__imp__o_strcat_s
0x18001afd1  xor     eax, eax
0x18001afd3  cmp     [r15+8], rax
0x18001afd7  jz      loc_18001B06D
0x18001afdd  cmp     [r15], ax
0x18001afe1  jz      short loc_18001B061
0x18001afe3  lea     rdx, [rbp+var_28]
0x18001afe7  mov     rcx, r15
0x18001afea  call    BackslashEncodeString
0x18001afef  mov     ebx, eax
0x18001aff1  test    eax, eax
0x18001aff3  jns     short loc_18001B033
0x18001aff5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001affc  lea     r13, WPP_GLOBAL_Control
0x18001b003  cmp     rcx, r13
0x18001b006  jz      loc_18001B28E
0x18001b00c  test    byte ptr [rcx+1Ch], 1
0x18001b010  jz      loc_18001B28E
0x18001b016  mov     edx, 0BBh
0x18001b01b  mov     rcx, [rcx+10h]
0x18001b01f  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001b026  mov     r9d, eax
0x18001b029  call    WPP_SF_d
0x18001b02e  jmp     loc_18001B28E
0x18001b033  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b03a  lea     r13, WPP_GLOBAL_Control
0x18001b041  cmp     rcx, r13
0x18001b044  jz      loc_18001B10E
0x18001b04a  test    byte ptr [rcx+1Ch], 4
0x18001b04e  jz      loc_18001B10E
0x18001b054  mov     edx, 0BCh
0x18001b059  mov     r9, r15
0x18001b05c  jmp     loc_18001B0F5
0x18001b061  lea     r8, aRealm; ",realm=\"\""
0x18001b068  jmp     loc_18001B157
0x18001b06d  cmp     [rbp+arg_18], 4
0x18001b071  jnz     loc_18001B139
0x18001b077  cmp     dword ptr [r14+3Ch], 2
0x18001b07c  jnz     loc_18001B139
0x18001b082  cmp     word ptr cs:g_strNtDigestUTF8ServerRealm, ax
0x18001b089  jz      loc_18001B163
0x18001b08f  lea     rdx, [rbp+var_28]
0x18001b093  lea     rcx, g_strNtDigestUTF8ServerRealm
0x18001b09a  call    BackslashEncodeString
0x18001b09f  mov     ebx, eax
0x18001b0a1  test    eax, eax
0x18001b0a3  jns     short loc_18001B0D0
0x18001b0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0ac  lea     r13, WPP_GLOBAL_Control
0x18001b0b3  cmp     rcx, r13
0x18001b0b6  jz      loc_18001B28E
0x18001b0bc  test    byte ptr [rcx+1Ch], 1
0x18001b0c0  jz      loc_18001B28E
0x18001b0c6  mov     edx, 0BDh
0x18001b0cb  jmp     loc_18001B01B
0x18001b0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0d7  lea     r13, WPP_GLOBAL_Control
0x18001b0de  cmp     rcx, r13
0x18001b0e1  jz      short loc_18001B10E
0x18001b0e3  test    byte ptr [rcx+1Ch], 4
0x18001b0e7  jz      short loc_18001B10E
0x18001b0e9  mov     edx, 0BEh
0x18001b0ee  lea     r9, g_strNtDigestUTF8ServerRealm
0x18001b0f5  mov     rcx, [rcx+10h]
0x18001b0f9  lea     rax, [rbp+var_28]
0x18001b0fd  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001b104  mov     [rsp+58h+var_38], rax
0x18001b109  call    WPP_SF_aZaZ
0x18001b10e  lea     r9, [rbp+var_28]
0x18001b112  mov     edx, 1001h; BufferCount
0x18001b117  lea     r8, aRealmHz; ",realm=\"%hZ\""
0x18001b11e  mov     rcx, rsi; Buffer
0x18001b121  call    sprintf_s
0x18001b126  mov     r8, rsi
0x18001b129  mov     edx, 3001h
0x18001b12e  mov     rcx, rdi
0x18001b131  call    cs:__imp__o_strcat_s
0x18001b137  jmp     short loc_18001B16A
0x18001b139  lea     r9, aDigest_0; "Digest"
0x18001b140  mov     edx, 1001h; BufferCount
0x18001b145  lea     r8, aRealmS; ",realm=\"%s\""
0x18001b14c  mov     rcx, rsi; Buffer
0x18001b14f  call    sprintf_s
0x18001b154  mov     r8, rsi
0x18001b157  mov     rdx, r13
0x18001b15a  mov     rcx, rdi
0x18001b15d  call    cs:__imp__o_strcat_s
0x18001b163  lea     r13, WPP_GLOBAL_Control
0x18001b16a  movzx   eax, word ptr [rbp+Source]
0x18001b16e  test    ax, ax
0x18001b171  jz      short loc_18001B188
0x18001b173  mov     r8, [rbp+Source+8]; Source
0x18001b177  mov     r9d, eax; MaxCount
0x18001b17a  mov     edx, 3001h; SizeInBytes
0x18001b17f  mov     rcx, rdi; Destination
0x18001b182  call    cs:__imp_strncat_s
0x18001b188  test    dword ptr [r14+24h], 200000h
0x18001b190  jz      short loc_18001B1B7
0x18001b192  lea     r8, aStaleTrue; ",stale=true"
0x18001b199  mov     edx, 1001h; BufferCount
0x18001b19e  mov     rcx, rsi; Buffer
0x18001b1a1  call    sprintf_s
0x18001b1a6  mov     r8, rsi
0x18001b1a9  mov     edx, 3001h
0x18001b1ae  mov     rcx, rdi
0x18001b1b1  call    cs:__imp__o_strcat_s
0x18001b1b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b1bb  xor     ecx, ecx
0x18001b1bd  inc     rax
0x18001b1c0  cmp     [rdi+rax], cl
0x18001b1c3  jnz     short loc_18001B1BD
0x18001b1c5  movzx   r14d, ax
0x18001b1c9  mov     eax, [r12]
0x18001b1cd  test    eax, eax
0x18001b1cf  jnz     short loc_18001B228
0x18001b1d1  mov     ecx, r14d; Size
0x18001b1d4  call    DigestAllocateMemory
0x18001b1d9  mov     [r12+8], rax
0x18001b1de  test    rax, rax
0x18001b1e1  jnz     short loc_18001B209
0x18001b1e3  mov     ebx, 80090300h
0x18001b1e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1ef  cmp     rcx, r13
0x18001b1f2  jz      loc_18001B28E
0x18001b1f8  test    byte ptr [rcx+1Ch], 1
0x18001b1fc  jz      loc_18001B28E
0x18001b202  mov     edx, 0C1h
0x18001b207  jmp     short loc_18001B27E
0x18001b209  mov     dword ptr [r12+4], 1
0x18001b212  mov     rcx, [r12+8]; void *
0x18001b217  mov     r8, r14; Size
0x18001b21a  mov     rdx, rdi; Src
0x18001b21d  call    memcpy_0
0x18001b222  mov     [r12], r14d
0x18001b226  jmp     short loc_18001B28E
0x18001b228  cmp     r14d, eax
0x18001b22b  jbe     short loc_18001B212
0x18001b22d  mov     ebx, 0C0000023h
0x18001b232  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b239  cmp     rcx, r13
0x18001b23c  jz      short loc_18001B28E
0x18001b23e  test    byte ptr [rcx+1Ch], 1
0x18001b242  jz      short loc_18001B28E
0x18001b244  mov     rcx, [rcx+10h]
0x18001b248  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001b24f  mov     edx, 0C2h
0x18001b254  mov     dword ptr [rsp+58h+var_38], eax
0x18001b258  mov     r9d, r14d
  ... truncated ...
```
