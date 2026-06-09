# WcnServiceMain

- ea: `0x1800054a0`
- end: `0x180005618`
- name: `WcnServiceMain`
- size: `376`
- prototype: `void()`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x180001404`
- `0x180002d60`
- `0x180003288`
- `0x180003b98`
- `0x180004f78`
- `0x180004fb8`
- `0x1800054a0`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800055c9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800055c9`

## string_xrefs

- `0x18000558e`: `g_pWcnService`

## pseudocode

```c
void WcnServiceMain()
{
  const char *Indent; // rax
  __int64 v1; // r10
  CWcnService *v2; // rax
  CWcnService *v3; // rcx
  int v4; // eax
  CWcnService *v5; // rbx
  const char *v6; // rax
  __int64 v7; // r10

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v1 + 16), 10, WPP_e688d21a23d1311573d345219b1a5aa8_Traceguids, Indent);
  }
  g_pWcnService = 0;
  if ( g_pSvchostGlobalData )
  {
    v2 = (CWcnService *)operator new(0x40u);
    if ( v2 )
    {
      *(_QWORD *)v2 = 0;
      *((_QWORD *)v2 + 5) = 0;
      *((_QWORD *)v2 + 6) = 0;
      *((_QWORD *)v2 + 7) = 0;
      g_pWcnService = v2;
      v4 = CWcnService::Init(v3);
      if ( v4 >= 0 )
      {
LABEL_16:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v6 = GetIndent(-1);
          WPP_SF_s(*(_QWORD *)(v7 + 16), 13, WPP_e688d21a23d1311573d345219b1a5aa8_Traceguids, v6);
        }
        return;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_e688d21a23d1311573d345219b1a5aa8_Traceguids,
          (unsigned int)v4);
    }
    else
    {
      g_pWcnService = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_e688d21a23d1311573d345219b1a5aa8_Traceguids,
          "g_pWcnService");
    }
    CWcnService::Shutdown(g_pWcnService);
    v5 = g_pWcnService;
    if ( g_pWcnService )
    {
      CWcnService::~CWcnService(g_pWcnService);
      operator delete(v5);
    }
    g_pWcnService = 0;
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x1800054a0  mov     [rsp+arg_0], rbx
0x1800054a5  push    rsi
0x1800054a6  sub     rsp, 20h
0x1800054aa  mov     r10, cs:WPP_GLOBAL_Control
0x1800054b1  lea     rsi, WPP_GLOBAL_Control
0x1800054b8  cmp     r10, rsi
0x1800054bb  jz      short loc_1800054E6
0x1800054bd  cmp     byte ptr [r10+19h], 6
0x1800054c2  jb      short loc_1800054E6
0x1800054c4  mov     ecx, 1; int
0x1800054c9  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800054ce  mov     rcx, [r10+10h]
0x1800054d2  lea     r8, WPP_e688d21a23d1311573d345219b1a5aa8_Traceguids
0x1800054d9  mov     edx, 0Ah
0x1800054de  mov     r9, rax
0x1800054e1  call    WPP_SF_s
0x1800054e6  cmp     cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, 0; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x1800054ee  mov     cs:?g_pWcnService@@3PEAVCWcnService@@EA, 0; CWcnService * g_pWcnService
0x1800054f9  jz      loc_18000560D
0x1800054ff  mov     ecx, 40h ; '@'; Size
0x180005504  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005509  test    rax, rax
0x18000550c  jz      short loc_18000556D
0x18000550e  mov     qword ptr [rax], 0
0x180005515  mov     qword ptr [rax+28h], 0
0x18000551d  mov     qword ptr [rax+30h], 0
0x180005525  mov     qword ptr [rax+38h], 0
0x18000552d  mov     cs:?g_pWcnService@@3PEAVCWcnService@@EA, rax; CWcnService * g_pWcnService
0x180005534  call    ?Init@CWcnService@@QEAAJXZ; CWcnService::Init(void)
0x180005539  test    eax, eax
0x18000553b  jns     loc_1800055DA
0x180005541  mov     rcx, cs:WPP_GLOBAL_Control
0x180005548  cmp     rcx, rsi
0x18000554b  jz      short loc_1800055A6
0x18000554d  cmp     byte ptr [rcx+19h], 2
0x180005551  jb      short loc_1800055A6
0x180005553  mov     rcx, [rcx+10h]
0x180005557  lea     r8, WPP_e688d21a23d1311573d345219b1a5aa8_Traceguids
0x18000555e  mov     edx, 0Ch
0x180005563  mov     r9d, eax
0x180005566  call    WPP_SF_d
0x18000556b  jmp     short loc_1800055A6
0x18000556d  mov     cs:?g_pWcnService@@3PEAVCWcnService@@EA, 0; CWcnService * g_pWcnService
0x180005578  mov     rcx, cs:WPP_GLOBAL_Control
0x18000557f  cmp     rcx, rsi
0x180005582  jz      short loc_1800055A6
0x180005584  cmp     byte ptr [rcx+19h], 2
0x180005588  jb      short loc_1800055A6
0x18000558a  mov     rcx, [rcx+10h]
0x18000558e  lea     r9, aGPwcnservice; "g_pWcnService"
0x180005595  mov     edx, 0Bh
0x18000559a  lea     r8, WPP_e688d21a23d1311573d345219b1a5aa8_Traceguids
0x1800055a1  call    WPP_SF_s
0x1800055a6  mov     rcx, cs:?g_pWcnService@@3PEAVCWcnService@@EA; this
0x1800055ad  call    ?Shutdown@CWcnService@@QEAAXXZ; CWcnService::Shutdown(void)
0x1800055b2  mov     rbx, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x1800055b9  test    rbx, rbx
0x1800055bc  jz      short loc_1800055CF
0x1800055be  mov     rcx, rbx; this
0x1800055c1  call    ??1CWcnService@@QEAA@XZ; CWcnService::~CWcnService(void)
0x1800055c6  mov     rcx, rbx
0x1800055c9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800055cf  mov     cs:?g_pWcnService@@3PEAVCWcnService@@EA, 0; CWcnService * g_pWcnService
0x1800055da  mov     r10, cs:WPP_GLOBAL_Control
0x1800055e1  cmp     r10, rsi
0x1800055e4  jz      short loc_18000560D
0x1800055e6  cmp     byte ptr [r10+19h], 6
0x1800055eb  jb      short loc_18000560D
0x1800055ed  or      ecx, 0FFFFFFFFh; int
0x1800055f0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800055f5  mov     rcx, [r10+10h]
0x1800055f9  lea     r8, WPP_e688d21a23d1311573d345219b1a5aa8_Traceguids
0x180005600  mov     edx, 0Dh
0x180005605  mov     r9, rax
0x180005608  call    WPP_SF_s
0x18000560d  mov     rbx, [rsp+28h+arg_0]
0x180005612  add     rsp, 20h
0x180005616  pop     rsi
0x180005617  retn
```
