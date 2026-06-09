# DvrInit(void)

- ea: `0x3838a0ef0`
- end: `0x3838a10b7`
- name: `?DvrInit@@YAKXZ`
- size: `455`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3838a1ae0`
- `0x38395cdc0`
- `0x38395d2c0`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x383844c00`
- `0x383844e18`
- `0x383892450`
- `0x383893160`
- `0x383893ff0`
- `0x383895640`
- `0x3838a0ef0`
- `0x3838a12a0`
- `0x38391ac10`
- `0x38391ac30`
- `0x38391ac40`
- `0x38391aed0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3838c5d3a`
- `KERNEL32!GetLastError` at `0x3838c5d78`
- `KERNEL32!GetLastError` at `0x3838c5e85`
- `KERNEL32!GetLastError` at `0x3838c5d3a`
- `KERNEL32!GetLastError` at `0x3838c5d78`
- `KERNEL32!GetLastError` at `0x3838c5e85`
- `KERNEL32!GetTempPathW` at `0x3838a1005`
- `KERNEL32!GetTempPathW` at `0x3838a1005`
- `KERNEL32!GetComputerNameW` at `0x3838a1168`
- `KERNEL32!GetComputerNameW` at `0x3838a1168`
- `USER32!LoadStringW` at `0x3838a118f`
- `USER32!LoadStringW` at `0x3838a118f`
- `ADVAPI32!GetUserNameW` at `0x3838a1146`
- `ADVAPI32!GetUserNameW` at `0x3838a1146`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 DvrInit(void)
{
  struct CCriticalSection **v0; // rdx
  struct CCriticalSection *CriticalSection; // rax
  unsigned int v2; // edi
  HINSTANCE v3; // rdx
  const unsigned __int16 *v4; // rcx
  HINSTANCE *v5; // r8
  __int64 v7; // rbx
  DWORD TempPathW; // eax
  __int64 v9; // r11
  WCHAR *v10; // rcx
  WCHAR v11; // ax
  WCHAR *v12; // rcx
  WCHAR v13; // ax
  unsigned __int64 v14; // rdx
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v16; // r8
  unsigned __int64 v17; // r9
  __int64 v18; // rbx
  int (* near **v19)(void); // rcx
  signed __int64 v20; // rdx
  WCHAR *v21; // r9
  wchar_t *v22; // r8
  __int64 v23; // rdx
  DWORD pcbBuffer; // [rsp+30h] [rbp-248h] BYREF
  __int64 v25; // [rsp+38h] [rbp-240h]
  __int64 v26; // [rsp+40h] [rbp-238h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF

  v26 = -2;
  v2 = 0;
  pcbBuffer = 0;
  memset(Buffer, 0, 522);
  v25 = -1;
  if ( (bidGblFlags & 4) != 0 && off_383B4A798[0] && bidID != -1 )
    off_383B15050();
  if ( (unsigned int)InitializeDll() )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)g_pcsGlobal + 4) + 8LL))((char *)g_pcsGlobal + 32);
    if ( (g_uInitializationStatus & 0x100) == 0 )
    {
      if ( !(unsigned int)InitializeSharedModules(v4, v3, v5) )
      {
        v2 = 1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B431C8, 5190665, off_383B49120[0], 5069);
        goto LABEL_6;
      }
      if ( g_pMPCritSecPool )
      {
        CMPCritSecPool::GetCritSecFromPool((CMPCritSecPool *)&g_csSQLPerf, v0);
        CriticalSection = (struct CCriticalSection *)g_csSQLPerf;
      }
      else
      {
        CriticalSection = CreateCriticalSection(0);
        g_csSQLPerf = CriticalSection;
      }
      if ( !CriticalSection )
      {
        v2 = 1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B431C8, 5197833, off_383B49120[0], 5076);
        goto LABEL_6;
      }
      g_uInitializationStatus |= 0x100u;
    }
    if ( g_cInitRefCount )
    {
      ++g_cInitRefCount;
      if ( (bidGblFlags & 2) != 0 && off_383B49298[0] )
        bidTraceW(off_383B431C8, 5209088, off_383B49298[0], (unsigned int)g_cInitRefCount);
      goto LABEL_6;
    }
    v7 = 261;
    TempPathW = GetTempPathW(0x105u, Buffer);
    if ( TempPathW && TempPathW < 0x105 )
    {
      if ( (unsigned __int64)TempPathW + 10 > 0x105 )
      {
        v2 = 1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B431C8, 5230601, off_383B49120[0], 5108);
        goto LABEL_6;
      }
      StringCchPrintfW(&g_szDefPerfDataFile, 0x105u, L"%s%s", Buffer, L"STATS.LOG");
      StringCchPrintfW(&g_szDefPerfQueryFile, 0x105u, L"%s%s", Buffer, L"QUERY.LOG");
      v9 = 261;
      v10 = &g_szPerfQueryFile;
      while ( v9 != -2147483385 )
      {
        v11 = *(WCHAR *)((char *)v10 + (char *)&g_szDefPerfQueryFile - (char *)&g_szPerfQueryFile);
        if ( !v11 )
          break;
        *v10++ = v11;
        if ( !--v9 )
        {
          --v10;
          break;
        }
      }
      *v10 = 0;
      v12 = &g_szPerfDataFile;
      while ( v7 != -2147483385 )
      {
        v13 = *(WCHAR *)((char *)v12 + (char *)&g_szDefPerfDataFile - (char *)&g_szPerfDataFile);
        if ( !v13 )
          break;
        *v12++ = v13;
        if ( !--v7 )
        {
          --v12;
          break;
        }
      }
      *v12 = 0;
      pcbBuffer = 257;
      if ( GetUserNameW(&g_szUserName, &pcbBuffer) )
      {
        pcbBuffer = 257;
        if ( GetComputerNameW(&g_szComputerName, &pcbBuffer) )
        {
          pcbBuffer = LoadStringW(g_hinstance_language, 0x9C46u, &g_wszLocal, 30);
          GetAppName(v15, v14, v16, v17);
          memset(&g_SQLPerfData, 0, sizeof(g_SQLPerfData));
          if ( !g_pTdsParser )
          {
            v18 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 208);
            if ( v18 )
            {
              *(_QWORD *)v18 = &CTdsParser::`vftable';
              *(_QWORD *)(v18 + 152) = 0;
              *(_DWORD *)(v18 + 160) = 0;
              *(_DWORD *)(v18 + 164) = 0;
              *(_DWORD *)(v18 + 168) = 0;
              *(_QWORD *)(v18 + 172) = 0;
              *(_QWORD *)(v18 + 180) = 0;
              *(_DWORD *)(v18 + 188) = 0;
              *(_DWORD *)(v18 + 192) = 1;
              memset((void *)(v18 + 8), 0, 0x90u);
            }
            else
            {
              v18 = 0;
            }
            g_pTdsParser = (CTdsParser *)v18;
            if ( !v18 )
            {
              v2 = 1;
              if ( (bidGblFlags & 2) != 0 && off_383B49278[0] && bidID != -1 )
                off_383B15040();
              goto LABEL_6;
            }
            if ( (int)CTdsParser::InitParser((CTdsParser *)v18) < 0 )
            {
              if ( g_pTdsParser )
                (**(void (__fastcall ***)(CTdsParser *, __int64))g_pTdsParser)(g_pTdsParser, 1);
              g_pTdsParser = 0;
              v2 = 1;
              goto LABEL_6;
            }
            v19 = &g_rgTdsHandlers;
            v20 = g_pTdsParser - (CTdsParser *)&g_rgTdsHandlers;
            do
            {
              *(int (* near **)(void))((char *)v19 + v20 + 8) = *v19;
              ++v19;
            }
            while ( (__int64)v19 < (__int64)&dword_383B15FF0 );
          }
          g_cInitRefCount = 1;
LABEL_6:
          (*(void (__fastcall **)(char *))(*((_QWORD *)g_pcsGlobal + 4) + 24LL))((char *)g_pcsGlobal + 32);
          if ( v25 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
            off_383B15058();
          return v2;
        }
        v2 = 1;
        if ( (bidGblFlags & 2) == 0 || !off_383B49280[0] )
          goto LABEL_6;
        GetLastError();
        v21 = &g_szComputerName;
        v22 = off_383B49280[0];
        v23 = 5264384;
      }
      else
      {
        v2 = 1;
        if ( (bidGblFlags & 2) == 0 || !off_383B49288[0] )
          goto LABEL_6;
        GetLastError();
        v21 = &g_szUserName;
        v22 = off_383B49288[0];
        v23 = 5255168;
      }
    }
    else
    {
      v2 = 1;
      if ( (bidGblFlags & 2) == 0 || !off_383B49290[0] )
        goto LABEL_6;
      GetLastError();
      v21 = Buffer;
      v22 = off_383B49290[0];
      v23 = 5221376;
    }
    bidTraceW(off_383B431C8, v23, v22, v21);
    goto LABEL_6;
  }
  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
    bidTraceW(off_383B431C8, 5178377, off_383B49120[0], 5057);
  return 1;
}

```

## disassembly

```asm
0x3838a0ef0  mov     rax, rsp
0x3838a0ef3  push    r14
0x3838a0ef5  sub     rsp, 270h
0x3838a0efc  mov     [rsp+278h+var_238], 0FFFFFFFFFFFFFFFEh
0x3838a0f05  mov     [rax+8], rbx
0x3838a0f09  mov     [rax+10h], rbp
0x3838a0f0d  mov     [rax+18h], rsi
0x3838a0f11  mov     [rax+20h], rdi
0x3838a0f15  mov     rax, cs:__security_cookie
0x3838a0f1c  xor     rax, rsp
0x3838a0f1f  mov     [rsp+278h+var_18], rax
0x3838a0f27  xor     ebp, ebp
0x3838a0f29  mov     edi, ebp
0x3838a0f2b  mov     [rsp+278h+pcbBuffer], ebp
0x3838a0f2f  mov     [rsp+278h+Buffer], bp
0x3838a0f34  xor     edx, edx; Val
0x3838a0f36  mov     r8d, 208h; Size
0x3838a0f3c  lea     rcx, [rsp+278h+var_226]; void *
0x3838a0f41  call    memset
0x3838a0f46  mov     [rsp+278h+var_240], 0FFFFFFFFFFFFFFFFh
0x3838a0f4f  test    byte ptr cs:_bidGblFlags, 4
0x3838a0f56  jnz     loc_3838C5B7F
0x3838a0f5c  call    ?InitializeDll@@YAHXZ; InitializeDll(void)
0x3838a0f61  test    eax, eax
0x3838a0f63  jz      loc_3838C5BCB
0x3838a0f69  mov     rcx, cs:?g_pcsGlobal@@3PEAVCCriticalSection@@EA; CCriticalSection * g_pcsGlobal
0x3838a0f70  add     rcx, 20h ; ' '
0x3838a0f74  mov     rax, [rcx]
0x3838a0f77  call    qword ptr [rax+8]
0x3838a0f7a  mov     r11d, cs:?g_uInitializationStatus@@3KC; ulong volatile g_uInitializationStatus
0x3838a0f81  bt      r11d, 8
0x3838a0f86  jnb     loc_3838A0E94
0x3838a0f8c  mov     eax, cs:?g_cInitRefCount@@3JA; long g_cInitRefCount
0x3838a0f92  test    eax, eax
0x3838a0f94  jz      short loc_3838A0FF9
0x3838a0f96  inc     eax
0x3838a0f98  mov     cs:?g_cInitRefCount@@3JA, eax; long g_cInitRefCount
0x3838a0f9e  test    byte ptr cs:_bidGblFlags, 2
0x3838a0fa5  jnz     loc_3838C5CD0
0x3838a0fab  mov     rcx, cs:?g_pcsGlobal@@3PEAVCCriticalSection@@EA; CCriticalSection * g_pcsGlobal
0x3838a0fb2  add     rcx, 20h ; ' '
0x3838a0fb6  mov     rax, [rcx]
0x3838a0fb9  call    qword ptr [rax+18h]
0x3838a0fbc  nop
0x3838a0fbd  cmp     [rsp+278h+var_240], 0FFFFFFFFFFFFFFFFh
0x3838a0fc3  jnz     loc_3838C5EB2
0x3838a0fc9  mov     eax, edi
0x3838a0fcb  mov     rcx, [rsp+278h+var_18]
0x3838a0fd3  xor     rcx, rsp; StackCookie
0x3838a0fd6  call    __security_check_cookie
0x3838a0fdb  lea     r11, [rsp+278h+var_8]
0x3838a0fe3  mov     rbx, [r11+10h]
0x3838a0fe7  mov     rbp, [r11+18h]
0x3838a0feb  mov     rsi, [r11+20h]
0x3838a0fef  mov     rdi, [r11+28h]
0x3838a0ff3  mov     rsp, r11
0x3838a0ff6  pop     r14
0x3838a0ff8  retn
0x3838a0ff9  lea     rdx, [rsp+278h+Buffer]; lpBuffer
0x3838a0ffe  mov     ebx, 105h
0x3838a1003  mov     ecx, ebx; nBufferLength
0x3838a1005  call    cs:__imp_GetTempPathW
0x3838a100b  test    eax, eax
0x3838a100d  jz      loc_3838C5E63
0x3838a1013  cmp     eax, ebx
0x3838a1015  jnb     loc_3838C5E63
0x3838a101b  mov     eax, eax
0x3838a101d  add     rax, 0Ah
0x3838a1021  cmp     rax, rbx
0x3838a1024  ja      loc_3838C5E1E
0x3838a102a  lea     rax, aStatsLog; "STATS.LOG"
0x3838a1031  mov     [rsp+278h+var_258], rax
0x3838a1036  lea     r9, [rsp+278h+Buffer]
0x3838a103b  lea     r8, aSS_7; "%s%s"
0x3838a1042  mov     edx, ebx; unsigned __int64
0x3838a1044  lea     rsi, ?g_szDefPerfDataFile@@3PAGA; ushort near * g_szDefPerfDataFile
0x3838a104b  mov     rcx, rsi; unsigned __int16 *
0x3838a104e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x3838a1053  lea     r11, aQueryLog; "QUERY.LOG"
0x3838a105a  mov     [rsp+278h+var_258], r11
0x3838a105f  lea     r9, [rsp+278h+Buffer]
0x3838a1064  lea     r8, aSS_7; "%s%s"
0x3838a106b  mov     edx, ebx; unsigned __int64
0x3838a106d  lea     r14, ?g_szDefPerfQueryFile@@3PAGA; ushort near * g_szDefPerfQueryFile
0x3838a1074  mov     rcx, r14; unsigned __int16 *
0x3838a1077  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x3838a107c  mov     r11d, ebx
0x3838a107f  lea     rcx, ?g_szPerfQueryFile@@3PAGA; ushort near * g_szPerfQueryFile
0x3838a1086  sub     r14, rcx
0x3838a1089  nop     dword ptr [rax+00000000h]
0x3838a1090  lea     rax, [r11+7FFFFEF9h]
0x3838a1097  test    rax, rax
0x3838a109a  jz      short loc_3838A10E4
0x3838a109c  movzx   eax, word ptr [r14+rcx]
0x3838a10a1  test    ax, ax
0x3838a10a4  jz      short loc_3838A10E4
0x3838a10a6  mov     [rcx], ax
0x3838a10a9  add     rcx, 2
0x3838a10ad  dec     r11
0x3838a10b0  jnz     short loc_3838A1090
0x3838a10b2  jmp     loc_3838C5D04
0x3838a0e94  call    ?InitializeSharedModules@@YAHXZ; InitializeSharedModules(void)
0x3838a0e99  test    eax, eax
0x3838a0e9b  jz      loc_3838C5C37
0x3838a0ea1  cmp     cs:?g_pMPCritSecPool@@3PEAVCMPCritSecPool@@EA, 0; CMPCritSecPool * g_pMPCritSecPool
0x3838a0ea9  jz      loc_3838C5C7A
0x3838a0eaf  lea     rcx, ?g_csSQLPerf@@3PEAVCCriticalSection@@EA; this
0x3838a0eb6  call    ?GetCritSecFromPool@CMPCritSecPool@@QEAA_NPEAPEAVCCriticalSection@@@Z; CMPCritSecPool::GetCritSecFromPool(CCriticalSection * *)
0x3838a0ebb  mov     rax, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x3838a0ec2  jmp     short $+2
0x3838a0ec4  test    rax, rax
0x3838a0ec7  jz      loc_3838C5C8D
0x3838a0ecd  or      cs:?g_uInitializationStatus@@3KC, 100h; ulong volatile g_uInitializationStatus
0x3838a0ed7  jmp     loc_3838A0F8C
0x3838a10e4  test    r11, r11
0x3838a10e7  jz      loc_3838C5D06
0x3838a10ed  mov     [rcx], bp
0x3838a10f0  lea     rcx, ?g_szPerfDataFile@@3PAGA; ushort near * g_szPerfDataFile
0x3838a10f7  sub     rsi, rcx
0x3838a10fa  nop     word ptr [rax+rax+00h]
0x3838a1100  lea     rax, [rbx+7FFFFEF9h]
0x3838a1107  test    rax, rax
0x3838a110a  jz      short loc_3838A1126
0x3838a110c  movzx   eax, word ptr [rsi+rcx]
0x3838a1110  test    ax, ax
0x3838a1113  jz      short loc_3838A1126
0x3838a1115  mov     [rcx], ax
0x3838a1118  add     rcx, 2
0x3838a111c  dec     rbx
0x3838a111f  jnz     short loc_3838A1100
0x3838a1121  jmp     loc_3838C5D0F
0x3838a1126  test    rbx, rbx
0x3838a1129  jz      loc_3838C5D11
0x3838a112f  mov     [rcx], bp
0x3838a1132  mov     [rsp+278h+pcbBuffer], 101h
0x3838a113a  lea     rdx, [rsp+278h+pcbBuffer]; pcbBuffer
0x3838a113f  lea     rcx, ?g_szUserName@@3PAGA; lpBuffer
0x3838a1146  call    cs:__imp_GetUserNameW
0x3838a114c  test    eax, eax
0x3838a114e  jz      loc_3838C5D1A
0x3838a1154  mov     [rsp+278h+pcbBuffer], 101h
0x3838a115c  lea     rdx, [rsp+278h+pcbBuffer]; nSize
0x3838a1161  lea     rcx, ?g_szComputerName@@3PAGA; lpBuffer
0x3838a1168  call    cs:__imp_GetComputerNameW
0x3838a116e  test    eax, eax
0x3838a1170  jz      loc_3838C5D58
0x3838a1176  mov     r9d, 1Eh; cchBufferMax
0x3838a117c  lea     r8, ?g_wszLocal@@3PAGA; lpBuffer
0x3838a1183  mov     edx, 9C46h; uID
0x3838a1188  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x3838a118f  call    cs:__imp_LoadStringW
0x3838a1195  mov     [rsp+278h+pcbBuffer], eax
0x3838a1199  call    ?GetAppName@@YAHPEAG_K01@Z; GetAppName(ushort *,unsigned __int64,ushort *,unsigned __int64)
0x3838a119e  xor     edx, edx; Val
0x3838a11a0  mov     r8d, 0A0h; Size
0x3838a11a6  lea     rcx, ?g_SQLPerfData@@3Usqlperf@@A; void *
0x3838a11ad  call    memset
0x3838a11b2  cmp     cs:?g_pTdsParser@@3PEAVCTdsParser@@EA, 0; CTdsParser * g_pTdsParser
0x3838a11ba  jnz     loc_3838A1280
0x3838a11c0  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838a11c7  mov     rax, [rcx]
0x3838a11ca  mov     edx, 0D0h
0x3838a11cf  call    qword ptr [rax+58h]
0x3838a11d2  mov     rbx, rax
0x3838a11d5  test    rax, rax
0x3838a11d8  jz      loc_3838C5D96
0x3838a11de  lea     rax, ??_7CTdsParser@@6B@; const CTdsParser::`vftable'
0x3838a11e5  mov     [rbx], rax
0x3838a11e8  mov     [rbx+98h], rbp
0x3838a11ef  mov     [rbx+0A0h], ebp
0x3838a11f5  mov     [rbx+0A4h], ebp
0x3838a11fb  mov     [rbx+0A8h], ebp
0x3838a1201  mov     [rbx+0ACh], rbp
0x3838a1208  mov     [rbx+0B4h], rbp
0x3838a120f  mov     [rbx+0BCh], ebp
0x3838a1215  mov     dword ptr [rbx+0C0h], 1
0x3838a121f  lea     rcx, [rbx+8]; void *
0x3838a1223  xor     edx, edx; Val
0x3838a1225  mov     r8d, 90h; Size
0x3838a122b  call    memset
0x3838a1230  jmp     short $+2
0x3838a1232  mov     cs:?g_pTdsParser@@3PEAVCTdsParser@@EA, rbx; CTdsParser * g_pTdsParser
0x3838a1239  test    rbx, rbx
0x3838a123c  jz      loc_3838C5D9E
0x3838a1242  mov     rcx, rbx; this
0x3838a1245  call    ?InitParser@CTdsParser@@QEAAJXZ; CTdsParser::InitParser(void)
0x3838a124a  test    eax, eax
0x3838a124c  js      loc_3838C5DF7
0x3838a1252  lea     rcx, ?g_rgTdsHandlers@@3PAP6AJXZA; long (*near * g_rgTdsHandlers)(void)
0x3838a1259  mov     rdx, cs:?g_pTdsParser@@3PEAVCTdsParser@@EA; CTdsParser * g_pTdsParser
0x3838a1260  sub     rdx, rcx
0x3838a1263  lea     r8, dword_383B15FF0
0x3838a126a  nop     word ptr [rax+rax]
0x3838a126f  mov     rax, [rcx]
0x3838a1272  mov     [rdx+rcx+8], rax
0x3838a1277  add     rcx, 8
0x3838a127b  cmp     rcx, r8
0x3838a127e  jl      short loc_3838A126F
0x3838a1280  mov     cs:?g_cInitRefCount@@3JA, 1; long g_cInitRefCount
0x3838a128a  jmp     loc_3838A0FAB
0x3838c5b7f  mov     rax, cs:off_383B4A798; "<DvrInit|ODBC|DRIVER> "
0x3838c5b86  test    rax, rax
0x3838c5b89  jz      loc_3838A0F5C
0x3838c5b8f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3838c5b97  jz      loc_3838A0F5C
0x3838c5b9d  mov     [rsp+278h+var_250], rbp
0x3838c5ba2  mov     rax, cs:off_383B4A798; "<DvrInit|ODBC|DRIVER> "
0x3838c5ba9  mov     [rsp+278h+var_258], rax
0x3838c5bae  lea     r9, [rsp+278h+var_240]
0x3838c5bb3  xor     r8d, r8d
0x3838c5bb6  xor     edx, edx
0x3838c5bb8  mov     rcx, cs:_bidID
0x3838c5bbf  call    cs:off_383B15050
0x3838c5bc5  nop
0x3838c5bc6  jmp     loc_3838A0F5C
0x3838c5bcb  test    byte ptr cs:_bidGblFlags, 2
0x3838c5bd2  jz      short loc_3838C5BFF
0x3838c5bd4  mov     rcx, cs:off_383B431C8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838c5bdb  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3838c5be2  test    rax, rax
0x3838c5be5  jz      short loc_3838C5BFF
0x3838c5be7  mov     r9d, 13C1h
0x3838c5bed  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3838c5bf4  mov     edx, 4F0409h
0x3838c5bf9  call    _bidTraceW
0x3838c5bfe  nop
0x3838c5bff  cmp     [rsp+278h+var_240], 0FFFFFFFFFFFFFFFFh
0x3838c5c05  jz      short loc_3838C5C2D
0x3838c5c07  test    byte ptr cs:_bidGblFlags, 4
0x3838c5c0e  jz      short loc_3838C5C2D
0x3838c5c10  mov     rcx, cs:_bidID
0x3838c5c17  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838c5c1b  jz      short loc_3838C5C2D
0x3838c5c1d  lea     r9, [rsp+278h+var_240]
0x3838c5c22  xor     r8d, r8d
0x3838c5c25  xor     edx, edx
0x3838c5c27  call    cs:off_383B15058
0x3838c5c2d  mov     eax, 1
0x3838c5c32  jmp     loc_3838A0FCB
0x3838c5c37  lea     edi, [rax+1]
0x3838c5c3a  test    byte ptr cs:_bidGblFlags, 2
0x3838c5c41  jz      loc_3838A0FAB
0x3838c5c47  mov     rcx, cs:off_383B431C8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838c5c4e  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3838c5c55  test    rax, rax
0x3838c5c58  jz      loc_3838A0FAB
0x3838c5c5e  mov     r9d, 13CDh
0x3838c5c64  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3838c5c6b  mov     edx, 4F3409h
0x3838c5c70  call    _bidTraceW
0x3838c5c75  jmp     loc_3838A0FAB
0x3838c5c7a  xor     ecx, ecx; unsigned int
0x3838c5c7c  call    ?CreateCriticalSection@@YAPEAVCCriticalSection@@K@Z; CreateCriticalSection(ulong)
0x3838c5c81  mov     cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA, rax; CCriticalSection * g_csSQLPerf
0x3838c5c88  jmp     loc_3838A0EC4
0x3838c5c8d  lea     edi, [rax+1]
0x3838c5c90  test    byte ptr cs:_bidGblFlags, 2
0x3838c5c97  jz      loc_3838A0FAB
0x3838c5c9d  mov     rcx, cs:off_383B431C8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838c5ca4  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3838c5cab  test    rax, rax
0x3838c5cae  jz      loc_3838A0FAB
0x3838c5cb4  mov     r9d, 13D4h
0x3838c5cba  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3838c5cc1  mov     edx, 4F5009h
0x3838c5cc6  call    _bidTraceW
0x3838c5ccb  jmp     loc_3838A0FAB
0x3838c5cd0  mov     rax, cs:off_383B49298; "<DvrInit|ODBC|DRIVER> Initialization Re"...
0x3838c5cd7  test    rax, rax
0x3838c5cda  jz      loc_3838A0FAB
0x3838c5ce0  mov     r9d, cs:?g_cInitRefCount@@3JA; long g_cInitRefCount
0x3838c5ce7  mov     r8, cs:off_383B49298; "<DvrInit|ODBC|DRIVER> Initialization Re"...
0x3838c5cee  mov     edx, 4F7C00h
0x3838c5cf3  mov     rcx, cs:off_383B431C8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838c5cfa  call    _bidTraceW
0x3838c5cff  jmp     loc_3838A0FAB
0x3838c5d04  jmp     short $+2
0x3838c5d06  sub     rcx, 2
0x3838c5d0a  jmp     loc_3838A10ED
0x3838c5d0f  jmp     short $+2
0x3838c5d11  sub     rcx, 2
0x3838c5d15  jmp     loc_3838A112F
0x3838c5d1a  lea     edi, [rax+1]
0x3838c5d1d  test    byte ptr cs:_bidGblFlags, 2
0x3838c5d24  jz      loc_3838A0FAB
0x3838c5d2a  mov     rax, cs:off_383B49288; "<DvrInit|ERR> GetUserName failed. g_szU"...
0x3838c5d31  test    rax, rax
0x3838c5d34  jz      loc_3838A0FAB
0x3838c5d3a  call    cs:__imp_GetLastError
0x3838c5d40  lea     r9, ?g_szUserName@@3PAGA; ushort near * g_szUserName
0x3838c5d47  mov     r8, cs:off_383B49288; "<DvrInit|ERR> GetUserName failed. g_szU"...
0x3838c5d4e  mov     edx, 503000h
0x3838c5d53  jmp     loc_3838C5E9C
0x3838c5d58  lea     edi, [rax+1]
0x3838c5d5b  test    byte ptr cs:_bidGblFlags, 2
0x3838c5d62  jz      loc_3838A0FAB
0x3838c5d68  mov     rax, cs:off_383B49280; "<DvrInit|ERR> GetComputerName failed. g"...
0x3838c5d6f  test    rax, rax
0x3838c5d72  jz      loc_3838A0FAB
0x3838c5d78  call    cs:__imp_GetLastError
  ... truncated ...
```
