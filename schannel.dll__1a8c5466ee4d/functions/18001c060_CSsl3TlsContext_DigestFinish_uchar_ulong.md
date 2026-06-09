# CSsl3TlsContext::DigestFinish(uchar *,ulong)

- ea: `0x18001c060`
- end: `0x18001c47f`
- name: `?DigestFinish@CSsl3TlsContext@@IEAAKPEAEK@Z`
- size: `1055`
- prototype: `unsigned int __fastcall(CSsl3TlsContext *__hidden this, unsigned __int8 *Src, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f510`
- `0x18007c870`

## callees

- `0x1800165a4`
- `0x18001c060`
- `0x18001cc80`
- `0x1800214f0`
- `0x18004bca4`
- `0x180057c8c`
- `0x1800597b0`
- `0x18005a160`
- `0x18005f1e4`
- `0x180082788`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001c11a`
- `ntdll!RtlReleaseResource` at `0x18001c11a`
- `ntdll!RtlAcquireResourceShared` at `0x18001c0d0`
- `ntdll!RtlAcquireResourceShared` at `0x18001c0d0`
- `ntdll!RtlInitUnicodeString` at `0x18008bb31`
- `ntdll!RtlInitUnicodeString` at `0x18008bb3f`
- `ntdll!RtlInitUnicodeString` at `0x18008bb31`
- `ntdll!RtlInitUnicodeString` at `0x18008bb3f`
- `ncrypt!SslComputeFinishedHash` at `0x18001c105`
- `ncrypt!SslComputeFinishedHash` at `0x18001c105`

## pseudocode

```c
__int64 __fastcall CSsl3TlsContext::DigestFinish(CSsl3TlsContext *this, unsigned __int8 *Src, int a3, __int64 a4)
{
  int v4; // r14d
  unsigned int v5; // ebx
  int v8; // r14d
  __int64 *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r15d
  __int64 v12; // r9
  char v13; // r8
  __int64 v14; // rax
  unsigned __int8 v15; // dl
  char v16; // cl
  __int64 v17; // rax
  __int64 v18; // rcx
  const WCHAR *v19; // rdx
  const WCHAR *v20; // rbx
  __int64 v21; // rax
  unsigned int v22; // edi
  __int64 v23; // rdx
  int v24; // ebx
  int v25; // edi
  __int64 v26; // rbp
  size_t v28; // rbp
  __int64 v29; // r8
  __int64 v30; // [rsp+20h] [rbp-718h]
  __int64 v31; // [rsp+28h] [rbp-710h]
  struct _UNICODE_STRING v32; // [rsp+40h] [rbp-6F8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-6E8h] BYREF
  _BYTE v34[8]; // [rsp+60h] [rbp-6D8h] BYREF
  int v35; // [rsp+68h] [rbp-6D0h]
  int v36; // [rsp+6Ch] [rbp-6CCh]
  _BYTE Srca[40]; // [rsp+6E0h] [rbp-58h] BYREF

  v4 = *((_DWORD *)this + 22);
  v5 = 12;
  if ( (v4 & 0xF3FC0) == 0 )
    v5 = 36;
  if ( a3 == v5 )
  {
    v8 = v4 & 0xA2AA0;
    RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL), 1u);
    v9 = (__int64 *)*((_QWORD *)this + 1);
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    v11 = SslComputeFinishedHash(
            v10,
            *(_QWORD *)(*((_QWORD *)this + 14) + 32LL),
            *((_QWORD *)this + 289),
            Srca,
            v5,
            (unsigned int)(v8 != 0) + 1);
    RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL));
    if ( v11 )
    {
      LOBYTE(v12) = 51;
      CSslContext::SetErrorAndFatalAlert(this, 902, v11, v12);
      return v11;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
      v13 = 0;
      v14 = 0;
      do
      {
        v15 = Src[v14];
        v16 = Srca[v14];
        v14 = (unsigned int)(v14 + 1);
        v13 |= v16 ^ v15;
      }
      while ( (unsigned int)v14 < v5 );
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
        v17 = (*(__int64 (__fastcall **)(CSsl3TlsContext *))(*(_QWORD *)this + 352LL))(this);
        v18 = *((_QWORD *)this + 231);
        if ( !*(_WORD *)(v18 + 34) )
        {
          *(_WORD *)(v18 + 34) = 900;
          *(_DWORD *)(v18 + 36) = -2146893048;
        }
        *((_WORD *)this + 60) = 13058;
        v19 = &Class;
        v20 = &Class;
        if ( v17 )
          v20 = (const WCHAR *)v17;
        v21 = *((_QWORD *)this + 13);
        if ( v21 )
        {
          v22 = *(_DWORD *)(v21 + 276);
          v19 = (const WCHAR *)(v21 + 280);
        }
        else
        {
          v22 = 0;
        }
        if ( (g_dwEventLogging & 4) != 0 )
        {
          DestinationString = 0;
          v32 = 0;
          RtlInitUnicodeString(&DestinationString, v19);
          RtlInitUnicodeString(&v32, v20);
          LODWORD(v31) = 900;
          LODWORD(v30) = 51;
          SchEventWrite(&SSLEVENT_GENERATE_FATAL_ALERT, L"duddu", v22, &DestinationString, v30, v31, &v32);
        }
        memset_0(v34, 0, 0x680u);
        v23 = *((_QWORD *)this + 1);
        if ( v23 )
          v24 = *(_DWORD *)(v23 + 28);
        else
          v24 = 0;
        v25 = *((unsigned __int16 *)this + 17);
        v26 = *((_QWORD *)this + 232);
        v36 = *((_DWORD *)this + 4);
        v35 = v24;
        if ( v23 )
        {
          v29 = *((_QWORD *)this + 14);
          if ( v29 )
            CSchannelTelemetryContext::LogKeyExchange(
              (CSsl3TlsContext *)((char *)this + 144),
              *(_DWORD *)(v23 + 32),
              *(_DWORD *)(*(_QWORD *)(v29 + 40) + 8LL));
        }
        if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
        {
          *((_DWORD *)this + 47) = v36;
          *((_BYTE *)this + 260) = 51;
          *((_DWORD *)this + 64) = -2146893048;
          *((_DWORD *)this + 66) = 900;
          *((_DWORD *)this + 46) = v24;
          *((_DWORD *)this + 48) = v25;
          *((_QWORD *)this + 35) = v26;
          *((_BYTE *)this + 169) = 1;
        }
        CSchannelTelemetryContext::LogDebugTraceHandshakeInfo((CSsl3TlsContext *)((char *)this + 144), L"Fatal Error");
        return 2148074248LL;
      }
      else
      {
        if ( v8 )
        {
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
          }
          v28 = v5;
          memcpy_0((char *)this + 2140, Src, v5);
          *((_DWORD *)this + 544) = v5;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
          }
          v28 = v5;
          memcpy_0((char *)this + 2097, Src, v5);
          *((_DWORD *)this + 534) = v5;
        }
        if ( !*((_BYTE *)this + 2060) )
        {
          memcpy_0((char *)this + 2061, Srca, v28);
          *((_BYTE *)this + 2060) = 1;
          CSsl3TlsContext::SetTokenBindingEKM(this);
        }
        if ( *((_BYTE *)this + 1953) && (*((_DWORD *)this + 22) & 0xA0000) != 0 )
          CSsl3TlsContext::FreeSavedWriteCipherState(this);
        return 0;
      }
    }
  }
  else
  {
    LOBYTE(a4) = 50;
    CSslContext::SetErrorAndFatalAlert(this, 903, 2148074248LL, a4);
    return 2148074248LL;
  }
}

```

## disassembly

```asm
0x18001c060  mov     r11, rsp
0x18001c063  push    rbx
0x18001c064  push    rsi
0x18001c065  push    rdi
0x18001c066  push    r14
0x18001c068  sub     rsp, 718h
0x18001c06f  mov     rax, cs:__security_cookie
0x18001c076  xor     rax, rsp
0x18001c079  mov     [rsp+738h+var_30], rax
0x18001c081  mov     r14d, [rcx+58h]
0x18001c085  mov     ebx, 0Ch
0x18001c08a  test    r14d, 0F3FC0h
0x18001c091  mov     eax, 24h ; '$'
0x18001c096  mov     rdi, rdx
0x18001c099  mov     rsi, rcx
0x18001c09c  cmovz   ebx, eax
0x18001c09f  cmp     r8d, ebx
0x18001c0a2  jnz     loc_18001C335
0x18001c0a8  mov     rax, [rcx+70h]
0x18001c0ac  and     r14d, 0A2AA0h
0x18001c0b3  mov     [r11+18h], rbp
0x18001c0b7  mov     dl, 1; Wait
0x18001c0b9  mov     ebp, 0
0x18001c0be  mov     [r11-28h], r15
0x18001c0c2  setnz   bpl
0x18001c0c6  mov     rcx, [rax+28h]
0x18001c0ca  inc     ebp
0x18001c0cc  add     rcx, 50h ; 'P'; Resource
0x18001c0d0  call    cs:__imp_RtlAcquireResourceShared
0x18001c0d6  mov     rax, [rsi+70h]
0x18001c0da  mov     rdx, [rax+20h]
0x18001c0de  mov     rax, [rsi+8]
0x18001c0e2  test    rax, rax
0x18001c0e5  jz      loc_18001C32E
0x18001c0eb  mov     rcx, [rax]
0x18001c0ee  mov     r8, [rsi+908h]
0x18001c0f5  lea     r9, [rsp+738h+Src]
0x18001c0fd  mov     dword ptr [rsp+738h+var_710], ebp
0x18001c101  mov     dword ptr [rsp+738h+var_718], ebx
0x18001c105  call    cs:__imp_SslComputeFinishedHash
0x18001c10b  mov     rcx, [rsi+70h]
0x18001c10f  mov     r15d, eax
0x18001c112  mov     rcx, [rcx+28h]
0x18001c116  add     rcx, 50h ; 'P'; Resource
0x18001c11a  call    cs:__imp_RtlReleaseResource
0x18001c120  test    r15d, r15d
0x18001c123  jnz     loc_18001C352
0x18001c129  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c130  lea     rbp, WPP_GLOBAL_Control
0x18001c137  cmp     rcx, rbp
0x18001c13a  jnz     loc_18001C303
0x18001c140  xor     r8b, r8b
0x18001c143  xor     eax, eax
0x18001c145  nop     word ptr [rax+rax+00000000h]
0x18001c150  movzx   edx, byte ptr [rax+rdi]
0x18001c154  movzx   ecx, [rsp+rax+738h+Src]
0x18001c15c  inc     eax
0x18001c15e  xor     dl, cl
0x18001c160  or      r8b, dl
0x18001c163  cmp     eax, ebx
0x18001c165  jb      short loc_18001C150
0x18001c167  test    r8b, r8b
0x18001c16a  jz      loc_18001C283
0x18001c170  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c177  cmp     rcx, rbp
0x18001c17a  jnz     loc_18001C3EC
0x18001c180  mov     rax, [rsi]
0x18001c183  mov     rcx, rsi
0x18001c186  mov     rax, [rax+160h]
0x18001c18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c192  mov     rcx, [rsi+738h]
0x18001c199  mov     r14d, 384h
0x18001c19f  cmp     word ptr [rcx+22h], 0
0x18001c1a4  jnz     short loc_18001C1B2
0x18001c1a6  mov     [rcx+22h], r14w
0x18001c1ab  mov     dword ptr [rcx+24h], 80090308h
0x18001c1b2  test    rax, rax
0x18001c1b5  mov     word ptr [rsi+78h], 3302h
0x18001c1bb  lea     rdx, Class
0x18001c1c2  mov     rbx, rdx
0x18001c1c5  cmovnz  rbx, rax
0x18001c1c9  mov     rax, [rsi+68h]
0x18001c1cd  test    rax, rax
0x18001c1d0  jz      loc_18001C327
0x18001c1d6  mov     edi, [rax+114h]
0x18001c1dc  lea     rdx, [rax+118h]; SourceString
0x18001c1e3  test    cs:?g_dwEventLogging@@3KA, 4; ulong g_dwEventLogging
0x18001c1ea  jnz     loc_18008BB1C
0x18001c1f0  xor     edx, edx; Val
0x18001c1f2  lea     rcx, [rsp+738h+var_6D8]; void *
0x18001c1f7  mov     r8d, 680h; Size
0x18001c1fd  call    memset_0
0x18001c202  mov     rdx, [rsi+8]
0x18001c206  test    rdx, rdx
0x18001c209  jz      short loc_18001C27F
0x18001c20b  mov     ebx, [rdx+1Ch]
0x18001c20e  mov     eax, [rsi+10h]
0x18001c211  movzx   edi, word ptr [rsi+22h]
0x18001c215  mov     rbp, [rsi+740h]
0x18001c21c  mov     [rsp+738h+var_6D0+4], eax
0x18001c220  mov     [rsp+738h+var_6D0], ebx
0x18001c224  test    rdx, rdx
0x18001c227  jnz     loc_18001C410
0x18001c22d  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, 0; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x18001c234  lea     rcx, [rsi+90h]; this
0x18001c23b  jnz     loc_18001C439
0x18001c241  lea     rdx, aFatalError; "Fatal Error"
0x18001c248  call    ?LogDebugTraceHandshakeInfo@CSchannelTelemetryContext@@QEAAXQEAG@Z; CSchannelTelemetryContext::LogDebugTraceHandshakeInfo(ushort * const)
0x18001c24d  mov     eax, 80090308h
0x18001c252  mov     rbp, [rsp+738h+arg_10]
0x18001c25a  mov     r15, [rsp+738h+var_28]
0x18001c262  mov     rcx, [rsp+738h+var_30]
0x18001c26a  xor     rcx, rsp; StackCookie
0x18001c26d  call    __security_check_cookie
0x18001c272  add     rsp, 718h
0x18001c279  pop     r14
0x18001c27b  pop     rdi
0x18001c27c  pop     rsi
0x18001c27d  pop     rbx
0x18001c27e  retn
0x18001c27f  xor     ebx, ebx
0x18001c281  jmp     short loc_18001C20E
0x18001c283  test    r14d, r14d
0x18001c286  jz      loc_18001C36D
0x18001c28c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c293  cmp     rcx, rbp
0x18001c296  jz      short loc_18001C2A5
0x18001c298  test    dword ptr [rcx+1Ch], 800h
0x18001c29f  jnz     loc_18001C398
0x18001c2a5  lea     rcx, [rsi+85Ch]; void *
0x18001c2ac  mov     r8d, ebx; Size
0x18001c2af  mov     rdx, rdi; Src
0x18001c2b2  mov     ebp, ebx
0x18001c2b4  call    memcpy_0
0x18001c2b9  mov     [rsi+880h], ebx
0x18001c2bf  cmp     byte ptr [rsi+80Ch], 0
0x18001c2c6  jnz     short loc_18001C2EE
0x18001c2c8  lea     rcx, [rsi+80Dh]; void *
0x18001c2cf  mov     r8, rbp; Size
0x18001c2d2  lea     rdx, [rsp+738h+Src]; Src
0x18001c2da  call    memcpy_0
0x18001c2df  mov     rcx, rsi; this
0x18001c2e2  mov     byte ptr [rsi+80Ch], 1
0x18001c2e9  call    ?SetTokenBindingEKM@CSsl3TlsContext@@IEAAKXZ; CSsl3TlsContext::SetTokenBindingEKM(void)
0x18001c2ee  cmp     byte ptr [rsi+7A1h], 0
0x18001c2f5  jnz     loc_18001C3D2
0x18001c2fb  mov     eax, r15d
0x18001c2fe  jmp     loc_18001C252
0x18001c303  test    byte ptr [rcx+1Ch], 4
0x18001c307  jz      loc_18001C140
0x18001c30d  mov     rcx, [rcx+10h]
0x18001c311  lea     r8, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids
0x18001c318  mov     edx, 3Dh ; '='
0x18001c31d  call    WPP_SF_
0x18001c322  jmp     loc_18001C140
0x18001c327  xor     edi, edi
0x18001c329  jmp     loc_18001C1E3
0x18001c32e  xor     ecx, ecx
0x18001c330  jmp     loc_18001C0EE
0x18001c335  mov     r9b, 32h ; '2'
0x18001c338  mov     edx, 387h
0x18001c33d  mov     r8d, 80090308h
0x18001c343  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18001c348  mov     eax, 80090308h
0x18001c34d  jmp     loc_18001C262
0x18001c352  mov     r9b, 33h ; '3'
0x18001c355  mov     r8d, r15d
0x18001c358  mov     edx, 386h
0x18001c35d  mov     rcx, rsi
0x18001c360  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18001c365  mov     eax, r15d
0x18001c368  jmp     loc_18001C252
0x18001c36d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c374  cmp     rcx, rbp
0x18001c377  jnz     short loc_18001C3B2
0x18001c379  lea     rcx, [rsi+831h]; void *
0x18001c380  mov     r8d, ebx; Size
0x18001c383  mov     rdx, rdi; Src
0x18001c386  mov     ebp, ebx
0x18001c388  call    memcpy_0
0x18001c38d  mov     [rsi+858h], ebx
0x18001c393  jmp     loc_18001C2BF
0x18001c398  mov     rcx, [rcx+10h]
0x18001c39c  lea     r8, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids
0x18001c3a3  mov     edx, 3Fh ; '?'
0x18001c3a8  call    WPP_SF_
0x18001c3ad  jmp     loc_18001C2A5
0x18001c3b2  test    dword ptr [rcx+1Ch], 800h
0x18001c3b9  jz      short loc_18001C379
0x18001c3bb  mov     rcx, [rcx+10h]
0x18001c3bf  lea     r8, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids
0x18001c3c6  mov     edx, 40h ; '@'
0x18001c3cb  call    WPP_SF_
0x18001c3d0  jmp     short loc_18001C379
0x18001c3d2  test    dword ptr [rsi+58h], 0A0000h
0x18001c3d9  jz      loc_18001C2FB
0x18001c3df  mov     rcx, rsi; this
0x18001c3e2  call    ?FreeSavedWriteCipherState@CSsl3TlsContext@@QEAAXXZ; CSsl3TlsContext::FreeSavedWriteCipherState(void)
0x18001c3e7  jmp     loc_18001C2FB
0x18001c3ec  test    byte ptr [rcx+1Ch], 1
0x18001c3f0  jz      loc_18001C180
0x18001c3f6  mov     rcx, [rcx+10h]
0x18001c3fa  lea     r8, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids
0x18001c401  mov     edx, 3Eh ; '>'
0x18001c406  call    WPP_SF_
0x18001c40b  jmp     loc_18001C180
0x18001c410  mov     r8, [rsi+70h]
0x18001c414  test    r8, r8
0x18001c417  jz      loc_18001C22D
0x18001c41d  mov     r8, [r8+28h]
0x18001c421  lea     rcx, [rsi+90h]; this
0x18001c428  mov     edx, [rdx+20h]; unsigned int
0x18001c42b  mov     r8d, [r8+8]; unsigned int
0x18001c42f  call    ?LogKeyExchange@CSchannelTelemetryContext@@QEAAXIK@Z; CSchannelTelemetryContext::LogKeyExchange(uint,ulong)
0x18001c434  jmp     loc_18001C22D
0x18001c439  mov     rdx, qword ptr [rsp+738h+var_6D0]
0x18001c43e  shr     rdx, 20h
0x18001c442  mov     [rsi+0BCh], edx
0x18001c448  mov     byte ptr [rsi+104h], 33h ; '3'
0x18001c44f  mov     dword ptr [rsi+100h], 80090308h
0x18001c459  mov     [rsi+108h], r14d
0x18001c460  mov     [rsi+0B8h], ebx
0x18001c466  mov     [rsi+0C0h], edi
0x18001c46c  mov     [rsi+118h], rbp
0x18001c473  mov     byte ptr [rsi+0A9h], 1
0x18001c47a  jmp     loc_18001C241
0x18008bb1c  xorps   xmm0, xmm0
0x18008bb1f  lea     rcx, [rsp+738h+DestinationString]; DestinationString
0x18008bb24  xorps   xmm1, xmm1
0x18008bb27  movups  xmmword ptr [rsp+738h+DestinationString.Length], xmm0
0x18008bb2c  movups  xmmword ptr [rsp+738h+var_6F8.Length], xmm1
0x18008bb31  call    cs:__imp_RtlInitUnicodeString
0x18008bb37  mov     rdx, rbx; SourceString
0x18008bb3a  lea     rcx, [rsp+738h+var_6F8]; DestinationString
0x18008bb3f  call    cs:__imp_RtlInitUnicodeString
0x18008bb45  lea     rax, [rsp+738h+var_6F8]
0x18008bb4a  mov     r8d, edi
0x18008bb4d  mov     [rsp+738h+var_708], rax
0x18008bb52  lea     r9, [rsp+738h+DestinationString]
0x18008bb57  mov     dword ptr [rsp+738h+var_710], r14d
0x18008bb5c  lea     rdx, aDuddu; "duddu"
0x18008bb63  lea     rcx, SSLEVENT_GENERATE_FATAL_ALERT; struct _EVENT_DESCRIPTOR *
0x18008bb6a  mov     dword ptr [rsp+738h+var_718], 33h ; '3'
0x18008bb72  call    ?SchEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SchEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x18008bb77  nop
0x18008bb78  jmp     loc_18001C1F0
```
