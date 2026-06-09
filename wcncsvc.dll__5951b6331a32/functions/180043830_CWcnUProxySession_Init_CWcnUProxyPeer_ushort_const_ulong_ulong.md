# CWcnUProxySession::Init(CWcnUProxyPeer *,ushort const *,ulong,ulong)

- ea: `0x180043830`
- end: `0x1800439d5`
- name: `?Init@CWcnUProxySession@@QEAAJPEAVCWcnUProxyPeer@@PEBGKK@Z`
- size: `421`
- prototype: `__int64 __fastcall(CWcnUProxySession *this, struct CWcnUProxyPeer *, const unsigned __int16 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180040e00`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x180043830`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180043915`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180043915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004392f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004392f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043939`

## pseudocode

```c
__int64 __fastcall CWcnUProxySession::Init(
        CWcnUProxySession *this,
        struct CWcnUProxyPeer *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5)
{
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  const char *v13; // r9
  signed int v15; // ebx
  __int64 v16; // rdi
  HANDLE EventW; // rax
  unsigned int LastError; // ebx
  _BYTE *v19; // r10
  unsigned int v20; // eax
  __int64 v21; // r10
  unsigned int v22; // eax
  __int64 v23; // r10

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 10, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 11;
    v13 = "pUProxyPeer";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v9 + 2), v12, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v13);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 12;
    v13 = "wszMacAddressString";
    goto LABEL_12;
  }
  v15 = 0;
  *((_QWORD *)this + 18) = a3;
  v16 = 0;
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 19) = a2;
  *((_DWORD *)this + 34) = a4;
  *((_DWORD *)this + 45) = a5;
  do
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + v16 + 3) = EventW;
    if ( EventW )
      goto LABEL_22;
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v15 = LastError | 0x80000000;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v21 + 16), 13, (unsigned int)WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v20, v15);
LABEL_22:
      v19 = WPP_GLOBAL_Control;
    }
    ++v16;
  }
  while ( v16 != 2 );
  if ( v19 != (_BYTE *)&WPP_GLOBAL_Control && (v15 < 0 || v19[25] >= 6u) )
  {
    v22 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v23 + 16), 14, (unsigned int)WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v22, v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180043830  push    rbx
0x180043832  push    rbp
0x180043833  push    rsi
0x180043834  push    rdi
0x180043835  push    r12
0x180043837  push    r14
0x180043839  push    r15
0x18004383b  sub     rsp, 30h
0x18004383f  mov     r14d, r9d
0x180043842  mov     rdi, r8
0x180043845  mov     rbp, rdx
0x180043848  mov     rsi, rcx
0x18004384b  mov     r10, cs:WPP_GLOBAL_Control
0x180043852  lea     r15, WPP_GLOBAL_Control
0x180043859  lea     r12, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x180043860  cmp     r10, r15
0x180043863  jz      short loc_180043891
0x180043865  cmp     byte ptr [r10+19h], 6
0x18004386a  jb      short loc_180043891
0x18004386c  mov     ecx, 1; int
0x180043871  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180043876  mov     rcx, [r10+10h]
0x18004387a  mov     edx, 0Ah
0x18004387f  mov     r9, rax
0x180043882  mov     r8, r12
0x180043885  call    WPP_SF_s
0x18004388a  mov     r10, cs:WPP_GLOBAL_Control
0x180043891  test    rbp, rbp
0x180043894  jnz     short loc_1800438AE
0x180043896  cmp     r10, r15
0x180043899  jz      short loc_1800438D5
0x18004389b  cmp     byte ptr [r10+19h], 2
0x1800438a0  jb      short loc_1800438D5
0x1800438a2  lea     edx, [rbp+0Bh]
0x1800438a5  lea     r9, aPuproxypeer; "pUProxyPeer"
0x1800438ac  jmp     short loc_1800438C9
0x1800438ae  test    rdi, rdi
0x1800438b1  jnz     short loc_1800438DF
0x1800438b3  cmp     r10, r15
0x1800438b6  jz      short loc_1800438D5
0x1800438b8  cmp     byte ptr [r10+19h], 2
0x1800438bd  jb      short loc_1800438D5
0x1800438bf  lea     edx, [rdi+0Ch]
0x1800438c2  lea     r9, aWszmacaddresss; "wszMacAddressString"
0x1800438c9  mov     rcx, [r10+10h]
0x1800438cd  mov     r8, r12
0x1800438d0  call    WPP_SF_s
0x1800438d5  mov     eax, 80004003h
0x1800438da  jmp     loc_1800439C6
0x1800438df  mov     eax, [rsp+68h+arg_20]
0x1800438e6  xor     ebx, ebx
0x1800438e8  mov     [rsi+90h], rdi
0x1800438ef  xor     edi, edi
0x1800438f1  mov     [rsi+0B0h], bl
0x1800438f7  mov     [rsi+98h], rbp
0x1800438fe  mov     [rsi+88h], r14d
0x180043905  mov     [rsi+0B4h], eax
0x18004390b  xor     r9d, r9d; lpName
0x18004390e  xor     r8d, r8d; bInitialState
0x180043911  xor     edx, edx; bManualReset
0x180043913  xor     ecx, ecx; lpEventAttributes
0x180043915  call    cs:__imp_CreateEventW
0x18004391b  mov     [rsi+rdi*8+18h], rax
0x180043920  test    rax, rax
0x180043923  jnz     short loc_180043980
0x180043925  call    cs:__imp_GetLastError
0x18004392b  test    eax, eax
0x18004392d  jg      short loc_180043939
0x18004392f  call    cs:__imp_GetLastError
0x180043935  mov     ebx, eax
0x180043937  jmp     short loc_180043948
0x180043939  call    cs:__imp_GetLastError
0x18004393f  movzx   ebx, ax
0x180043942  or      ebx, 80070000h
0x180043948  or      ebx, 80000000h
0x18004394e  mov     r10, cs:WPP_GLOBAL_Control
0x180043955  cmp     r10, r15
0x180043958  jz      short loc_180043987
0x18004395a  cmp     byte ptr [r10+19h], 2
0x18004395f  jb      short loc_180043987
0x180043961  xor     ecx, ecx; int
0x180043963  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180043968  mov     rcx, [r10+10h]
0x18004396c  mov     edx, 0Dh
0x180043971  mov     r9, rax
0x180043974  mov     [rsp+68h+var_48], ebx
0x180043978  mov     r8, r12
0x18004397b  call    WPP_SF_sd
0x180043980  mov     r10, cs:WPP_GLOBAL_Control
0x180043987  inc     rdi
0x18004398a  cmp     rdi, 2
0x18004398e  jnz     loc_18004390B
0x180043994  cmp     r10, r15
0x180043997  jz      short loc_1800439C4
0x180043999  test    ebx, ebx
0x18004399b  js      short loc_1800439A4
0x18004399d  cmp     byte ptr [r10+19h], 6
0x1800439a2  jb      short loc_1800439C4
0x1800439a4  or      ecx, 0FFFFFFFFh; int
0x1800439a7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800439ac  mov     rcx, [r10+10h]
0x1800439b0  mov     edx, 0Eh
0x1800439b5  mov     r9, rax
0x1800439b8  mov     [rsp+68h+var_48], ebx
0x1800439bc  mov     r8, r12
0x1800439bf  call    WPP_SF_sd
0x1800439c4  mov     eax, ebx
0x1800439c6  add     rsp, 30h
0x1800439ca  pop     r15
0x1800439cc  pop     r14
0x1800439ce  pop     r12
0x1800439d0  pop     rdi
0x1800439d1  pop     rsi
0x1800439d2  pop     rbp
0x1800439d3  pop     rbx
0x1800439d4  retn
```
