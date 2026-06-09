# CWcnUProxyPeer::TriggerSession(CWcnSession *,ulong,IWcnTransportSession * *)

- ea: `0x180040e00`
- end: `0x180041138`
- name: `?TriggerSession@CWcnUProxyPeer@@UEAAJPEAVCWcnSession@@KPEAPEAVIWcnTransportSession@@@Z`
- size: `824`
- prototype: `__int64 __fastcall(CWcnUProxyPeer *__hidden this, struct CWcnSession *, unsigned int, struct IWcnTransportSession **)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x180040e00`
- `0x180043830`
- `0x180053004`
- `0x1800567e4`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180040f27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180040f27`

## string_xrefs

- `0x180040ffe`: `pThreadpoolAdapter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWcnUProxyPeer::TriggerSession(
        CWcnUProxyPeer *this,
        struct CWcnSession *a2,
        unsigned int a3,
        struct _TP_WORK ***a4)
{
  _BYTE *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  const char *v12; // r9
  char *v14; // rsi
  struct _TP_WORK **v15; // rax
  struct _TP_WORK **v16; // rdi
  int v17; // ebx
  _BYTE *v18; // r10
  int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // r10

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 26, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 27;
    v12 = "pSession";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v8 + 2), v11, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, v12);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 28;
    v12 = "ppTransportSession";
    goto LABEL_12;
  }
  *a4 = 0;
  v14 = (char *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v14 )
  {
    *(_QWORD *)v14 = &CWcnUProxySession::`vftable';
    CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)(v14 + 40));
    *((_QWORD *)v14 + 19) = 0;
    v14[160] = 0;
    *((_QWORD *)v14 + 21) = 0;
    v14[176] = 0;
    *(_OWORD *)(v14 + 24) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v14 + 88));
  }
  else
  {
    v14 = 0;
  }
  v15 = (struct _TP_WORK **)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( v15 )
  {
    *v15 = (struct _TP_WORK *)&CWcnThreadpoolSession::`vftable'{for `IWcnTransportSession'};
    v15[4] = (struct _TP_WORK *)&CWcnThreadpoolSession::`vftable'{for `IWcnThreadpoolSessionCallback'};
    v15[7] = 0;
    v15[9] = 0;
    v15[10] = 0;
    *((_BYTE *)v15 + 88) = 0;
  }
  else
  {
    v16 = 0;
  }
  if ( v14 )
  {
    if ( !v16 )
    {
      v17 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids,
          "pThreadpoolAdapter");
      goto LABEL_37;
    }
    v19 = CWcnUProxySession::Init(
            (CWcnUProxySession *)v14,
            this,
            (const unsigned __int16 *)this + 46,
            *((_DWORD *)this + 22),
            a3);
    v17 = v19;
    if ( v19 >= 0 )
    {
      v19 = CWcnThreadpoolSession::Init(v16, a2, (struct IWcnLowLevelTransport *)v14, a3);
      v17 = v19;
      if ( v19 >= 0 )
      {
        *((_QWORD *)this + 5) = v14;
        *a4 = v16;
        goto LABEL_42;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_37;
      v21 = 32;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_37;
      v21 = 31;
    }
    WPP_SF_d(v20[2], v21, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, (unsigned int)v19);
LABEL_37:
    (**(void (__fastcall ***)(void *, __int64))v14)(v14, 1);
    goto LABEL_38;
  }
  v17 = -2147024882;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_39;
  WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, "pNewSession");
LABEL_38:
  v18 = WPP_GLOBAL_Control;
LABEL_39:
  if ( !v16 )
    goto LABEL_43;
  (*(void (__fastcall **)(struct _TP_WORK **, __int64))*v16)(v16, 1);
LABEL_42:
  v18 = WPP_GLOBAL_Control;
LABEL_43:
  if ( v18 != (_BYTE *)&WPP_GLOBAL_Control && (v17 < 0 || v18[25] >= 6u) )
  {
    v22 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v23 + 16), 33, (unsigned int)WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, v22, v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180040e00  mov     [rsp+arg_0], rbx
0x180040e05  mov     [rsp+arg_10], rbp
0x180040e0a  push    rsi
0x180040e0b  push    rdi
0x180040e0c  push    r12
0x180040e0e  push    r14
0x180040e10  push    r15
0x180040e12  sub     rsp, 40h
0x180040e16  mov     r14, r9
0x180040e19  mov     r12d, r8d
0x180040e1c  mov     r15, rdx
0x180040e1f  mov     rbp, rcx
0x180040e22  lea     rax, WPP_GLOBAL_Control
0x180040e29  mov     r10, cs:WPP_GLOBAL_Control
0x180040e30  cmp     r10, rax
0x180040e33  jz      short loc_180040E6C
0x180040e35  cmp     byte ptr [r10+19h], 6
0x180040e3a  jb      short loc_180040E6C
0x180040e3c  mov     ecx, 1; int
0x180040e41  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040e46  mov     edx, 1Ah
0x180040e4b  mov     r9, rax
0x180040e4e  lea     r8, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x180040e55  mov     rcx, [r10+10h]
0x180040e59  call    WPP_SF_s
0x180040e5e  mov     r10, cs:WPP_GLOBAL_Control
0x180040e65  lea     rax, WPP_GLOBAL_Control
0x180040e6c  test    r15, r15
0x180040e6f  jnz     short loc_180040E8A
0x180040e71  cmp     r10, rax
0x180040e74  jz      short loc_180040EB6
0x180040e76  cmp     byte ptr [r10+19h], 2
0x180040e7b  jb      short loc_180040EB6
0x180040e7d  lea     edx, [r15+1Bh]
0x180040e81  lea     r9, aPsession; "pSession"
0x180040e88  jmp     short loc_180040EA6
0x180040e8a  test    r14, r14
0x180040e8d  jnz     short loc_180040EC0
0x180040e8f  cmp     r10, rax
0x180040e92  jz      short loc_180040EB6
0x180040e94  cmp     byte ptr [r10+19h], 2
0x180040e99  jb      short loc_180040EB6
0x180040e9b  lea     edx, [r14+1Ch]
0x180040e9f  lea     r9, aPptransportses; "ppTransportSession"
0x180040ea6  lea     r8, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x180040ead  mov     rcx, [r10+10h]
0x180040eb1  call    WPP_SF_s
0x180040eb6  mov     eax, 80004003h
0x180040ebb  jmp     loc_18004111F
0x180040ec0  mov     qword ptr [r14], 0
0x180040ec7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180040ece  mov     ecx, 0B8h; unsigned __int64
0x180040ed3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180040ed8  mov     rsi, rax
0x180040edb  mov     [rsp+68h+arg_8], rax
0x180040ee0  test    rax, rax
0x180040ee3  jz      short loc_180040F30
0x180040ee5  lea     rax, ??_7CWcnUProxySession@@6B@; const CWcnUProxySession::`vftable'
0x180040eec  mov     [rsi], rax
0x180040eef  lea     rcx, [rsi+28h]; this
0x180040ef3  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x180040ef8  mov     qword ptr [rsi+98h], 0
0x180040f03  mov     byte ptr [rsi+0A0h], 0
0x180040f0a  mov     qword ptr [rsi+0A8h], 0
0x180040f15  mov     byte ptr [rsi+0B0h], 0
0x180040f1c  xorps   xmm0, xmm0
0x180040f1f  movups  xmmword ptr [rsi+18h], xmm0
0x180040f23  lea     rcx, [rsi+58h]; lpCriticalSection
0x180040f27  call    cs:__imp_InitializeCriticalSection
0x180040f2d  nop
0x180040f2e  jmp     short loc_180040F32
0x180040f30  xor     esi, esi
0x180040f32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180040f39  mov     ecx, 60h ; '`'; unsigned __int64
0x180040f3e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180040f43  mov     rdi, rax
0x180040f46  mov     [rsp+68h+arg_8], rax
0x180040f4b  test    rax, rax
0x180040f4e  jz      short loc_180040F83
0x180040f50  lea     rax, ??_7CWcnThreadpoolSession@@6BIWcnTransportSession@@@; const CWcnThreadpoolSession::`vftable'{for `IWcnTransportSession'}
0x180040f57  mov     [rdi], rax
0x180040f5a  lea     rax, ??_7CWcnThreadpoolSession@@6BIWcnThreadpoolSessionCallback@@@; const CWcnThreadpoolSession::`vftable'{for `IWcnThreadpoolSessionCallback'}
0x180040f61  mov     [rdi+20h], rax
0x180040f65  mov     qword ptr [rdi+38h], 0
0x180040f6d  mov     qword ptr [rdi+48h], 0
0x180040f75  mov     qword ptr [rdi+50h], 0
0x180040f7d  mov     byte ptr [rdi+58h], 0
0x180040f81  jmp     short loc_180040F85
0x180040f83  xor     edi, edi
0x180040f85  test    rsi, rsi
0x180040f88  jnz     short loc_180040FD0
0x180040f8a  mov     ebx, 8007000Eh
0x180040f8f  mov     r10, cs:WPP_GLOBAL_Control
0x180040f96  lea     rbp, WPP_GLOBAL_Control
0x180040f9d  cmp     r10, rbp
0x180040fa0  jz      loc_1800410BA
0x180040fa6  cmp     byte ptr [r10+19h], 2
0x180040fab  jb      loc_1800410BA
0x180040fb1  lea     edx, [rsi+1Dh]
0x180040fb4  lea     r9, aPnewsession; "pNewSession"
0x180040fbb  lea     r8, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x180040fc2  mov     rcx, [r10+10h]
0x180040fc6  call    WPP_SF_s
0x180040fcb  jmp     loc_1800410B3
0x180040fd0  test    rdi, rdi
0x180040fd3  jnz     short loc_18004101A
0x180040fd5  mov     ebx, 8007000Eh
0x180040fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fe1  lea     rbp, WPP_GLOBAL_Control
0x180040fe8  cmp     rcx, rbp
0x180040feb  jz      loc_1800410A0
0x180040ff1  cmp     byte ptr [rcx+19h], 2
0x180040ff5  jb      loc_1800410A0
0x180040ffb  lea     edx, [rdi+1Eh]
0x180040ffe  lea     r9, aPthreadpoolada; "pThreadpoolAdapter"
0x180041005  lea     r8, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x18004100c  mov     rcx, [rcx+10h]
0x180041010  call    WPP_SF_s
0x180041015  jmp     loc_1800410A0
0x18004101a  lea     r8, [rbp+5Ch]; unsigned __int16 *
0x18004101e  mov     [rsp+68h+var_48], r12d; unsigned int
0x180041023  mov     r9d, [rbp+58h]; unsigned int
0x180041027  mov     rdx, rbp; struct CWcnUProxyPeer *
0x18004102a  mov     rcx, rsi; this
0x18004102d  call    ?Init@CWcnUProxySession@@QEAAJPEAVCWcnUProxyPeer@@PEBGKK@Z; CWcnUProxySession::Init(CWcnUProxyPeer *,ushort const *,ulong,ulong)
0x180041032  mov     ebx, eax
0x180041034  test    eax, eax
0x180041036  jns     short loc_180041058
0x180041038  mov     rcx, cs:WPP_GLOBAL_Control
0x18004103f  lea     rbp, WPP_GLOBAL_Control
0x180041046  cmp     rcx, rbp
0x180041049  jz      short loc_1800410A0
0x18004104b  cmp     byte ptr [rcx+19h], 2
0x18004104f  jb      short loc_1800410A0
0x180041051  mov     edx, 1Fh
0x180041056  jmp     short loc_18004108D
0x180041058  mov     r9d, r12d; unsigned int
0x18004105b  mov     r8, rsi; struct IWcnLowLevelTransport *
0x18004105e  mov     rdx, r15; struct CWcnSession *
0x180041061  mov     rcx, rdi; this
0x180041064  call    ?Init@CWcnThreadpoolSession@@QEAAJPEAVCWcnSession@@PEAVIWcnLowLevelTransport@@K@Z; CWcnThreadpoolSession::Init(CWcnSession *,IWcnLowLevelTransport *,ulong)
0x180041069  mov     ebx, eax
0x18004106b  test    eax, eax
0x18004106d  jns     short loc_1800410D4
0x18004106f  mov     rcx, cs:WPP_GLOBAL_Control
0x180041076  lea     rbp, WPP_GLOBAL_Control
0x18004107d  cmp     rcx, rbp
0x180041080  jz      short loc_1800410A0
0x180041082  cmp     byte ptr [rcx+19h], 2
0x180041086  jb      short loc_1800410A0
0x180041088  mov     edx, 20h ; ' '
0x18004108d  mov     r9d, eax
0x180041090  lea     r8, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x180041097  mov     rcx, [rcx+10h]
0x18004109b  call    WPP_SF_d
0x1800410a0  mov     rax, [rsi]
0x1800410a3  mov     edx, 1
0x1800410a8  mov     rcx, rsi
0x1800410ab  mov     rax, [rax]
0x1800410ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410b3  mov     r10, cs:WPP_GLOBAL_Control
0x1800410ba  test    rdi, rdi
0x1800410bd  jz      short loc_1800410E9
0x1800410bf  mov     rax, [rdi]
0x1800410c2  mov     edx, 1
0x1800410c7  mov     rcx, rdi
0x1800410ca  mov     rax, [rax]
0x1800410cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410d2  jmp     short loc_1800410E2
0x1800410d4  mov     [rbp+28h], rsi
0x1800410d8  mov     [r14], rdi
0x1800410db  lea     rbp, WPP_GLOBAL_Control
0x1800410e2  mov     r10, cs:WPP_GLOBAL_Control
0x1800410e9  cmp     r10, rbp
0x1800410ec  jz      short loc_18004111D
0x1800410ee  test    ebx, ebx
0x1800410f0  js      short loc_1800410F9
0x1800410f2  cmp     byte ptr [r10+19h], 6
0x1800410f7  jb      short loc_18004111D
0x1800410f9  or      ecx, 0FFFFFFFFh; int
0x1800410fc  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180041101  mov     edx, 21h ; '!'
0x180041106  mov     [rsp+68h+var_48], ebx
0x18004110a  mov     r9, rax
0x18004110d  lea     r8, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x180041114  mov     rcx, [r10+10h]
0x180041118  call    WPP_SF_sd
0x18004111d  mov     eax, ebx
0x18004111f  lea     r11, [rsp+68h+var_28]
0x180041124  mov     rbx, [r11+30h]
0x180041128  mov     rbp, [r11+40h]
0x18004112c  mov     rsp, r11
0x18004112f  pop     r15
0x180041131  pop     r14
0x180041133  pop     r12
0x180041135  pop     rdi
0x180041136  pop     rsi
0x180041137  retn
```
