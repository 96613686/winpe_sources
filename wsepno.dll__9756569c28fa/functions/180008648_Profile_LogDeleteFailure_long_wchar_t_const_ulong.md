# Profile_LogDeleteFailure(long,wchar_t const *,ulong)

- ea: `0x180008648`
- end: `0x18000879f`
- name: `?Profile_LogDeleteFailure@@YAXJPEB_WK@Z`
- size: `343`
- prototype: `void __fastcall(DWORD dwMessageId, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800079f0`
- `0x1800080a0`

## callees

- `0x1800021f4`
- `0x180003be0`
- `0x180007768`
- `0x180008648`
- `0x18000890c`
- `0x18000c200`
- `0x18000c234`
- `0x18000c374`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800086f4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800086f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086fe`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000874e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000874e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Profile_LogDeleteFailure(DWORD dwMessageId, const wchar_t *a2)
{
  int v4; // eax
  const wchar_t *v5; // rdx
  signed int LastError; // eax
  wchar_t *v7; // rbx
  void *v8; // rdx
  WORD v9; // dx
  void *v10; // rdx
  void *lpMem; // [rsp+40h] [rbp-19h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v13; // [rsp+50h] [rbp-9h] BYREF
  int v14; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v15[64]; // [rsp+60h] [rbp+7h] BYREF
  int v16; // [rsp+A0h] [rbp+47h]

  v13 = 0;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v16 = 0;
  lpMem = 0;
  v4 = CAccountDisplayString::Initialize((wchar_t **)&lpMem, a2);
  v5 = &qword_180011360;
  if ( v4 >= 0 )
    v5 = (const wchar_t *)lpMem;
  CEventLog::CStrArray::Append((CEventLog::CStrArray *)&v14, v5);
  ProfNotifEventLog::Push(&v13, dwMessageId, 1);
  *(_QWORD *)Buffer = 0;
  if ( FormatMessageW(0x1100u, 0, dwMessageId, 0, Buffer, 1u, 0) )
  {
    v7 = 0;
    if ( *(_QWORD *)Buffer )
      v7 = *(wchar_t **)Buffer;
    goto LABEL_10;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v7 = 0;
  if ( LastError >= 0 )
  {
LABEL_10:
    CEventLog::CStrArray::Append((CEventLog::CStrArray *)&v14, v7);
    ProfNotif_HeapFree(v7, v8);
  }
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  v9 = 4;
  if ( !g_isPerUserCatalogEnabled )
    v9 = 1;
  ProfNotifEventLog::ReportEventW((ProfNotifEventLog *)&v13, v9, 0xC0000002);
  ProfNotif_HeapFree(lpMem, v10);
  CEventLog::~CEventLog((CEventLog *)&v13);
}

```

## disassembly

```asm
0x180008648  mov     [rsp-8+arg_10], rbx
0x18000864d  mov     [rsp-8+arg_18], rdi
0x180008652  push    rbp
0x180008653  lea     rbp, [rsp-57h]
0x180008658  sub     rsp, 0B0h
0x18000865f  mov     rbx, rdx
0x180008662  mov     edi, ecx
0x180008664  mov     [rbp+57h+var_60], 0
0x18000866c  mov     [rbp+57h+var_58], 0
0x180008673  xor     edx, edx; Val
0x180008675  lea     r8d, [rdx+40h]; Size
0x180008679  lea     rcx, [rbp+57h+var_50]; void *
0x18000867d  call    memset_0
0x180008682  mov     [rbp+57h+var_10], 0
0x180008689  mov     [rbp+57h+lpMem], 0
0x180008691  mov     rdx, rbx; wchar_t *
0x180008694  lea     rcx, [rbp+57h+lpMem]; this
0x180008698  call    ?Initialize@CAccountDisplayString@@QEAAJPEB_W@Z; CAccountDisplayString::Initialize(wchar_t const *)
0x18000869d  lea     rdx, qword_180011360
0x1800086a4  test    eax, eax
0x1800086a6  cmovns  rdx, [rbp+57h+lpMem]; wchar_t *
0x1800086ab  lea     rcx, [rbp+57h+var_58]; this
0x1800086af  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x1800086b4  mov     r8d, 1
0x1800086ba  mov     edx, edi
0x1800086bc  lea     rcx, [rbp+57h+var_60]
0x1800086c0  call    ?Push@ProfNotifEventLog@@QEAAJJW4eFmt@CEventLog@@@Z; ProfNotifEventLog::Push(long,CEventLog::eFmt)
0x1800086c5  mov     qword ptr [rbp+57h+Buffer], 0
0x1800086cd  mov     [rsp+0B0h+Arguments], 0; unsigned int
0x1800086d6  mov     [rsp+0B0h+nSize], 1; void *
0x1800086de  lea     rax, [rbp+57h+Buffer]
0x1800086e2  mov     [rsp+0B0h+lpBuffer], rax; void *
0x1800086e7  xor     r9d, r9d; dwLanguageId
0x1800086ea  mov     r8d, edi; dwMessageId
0x1800086ed  xor     edx, edx; lpSource
0x1800086ef  mov     ecx, 1100h; dwFlags
0x1800086f4  call    cs:__imp_FormatMessageW
0x1800086fa  test    eax, eax
0x1800086fc  jnz     short loc_180008718
0x1800086fe  call    cs:__imp_GetLastError
0x180008704  test    eax, eax
0x180008706  jle     short loc_180008710
0x180008708  movzx   eax, ax
0x18000870b  or      eax, 80070000h
0x180008710  xor     ebx, ebx
0x180008712  test    eax, eax
0x180008714  js      short loc_18000873A
0x180008716  jmp     short loc_180008726
0x180008718  xor     ebx, ebx
0x18000871a  mov     rax, qword ptr [rbp+57h+Buffer]
0x18000871e  test    rax, rax
0x180008721  jz      short loc_180008726
0x180008723  mov     rbx, rax
0x180008726  mov     rdx, rbx; wchar_t *
0x180008729  lea     rcx, [rbp+57h+var_58]; this
0x18000872d  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x180008732  mov     rcx, rbx; lpMem
0x180008735  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000873a  xor     r9d, r9d; Context
0x18000873d  xor     r8d, r8d; Parameter
0x180008740  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180008747  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18000874e  call    cs:__imp_InitOnceExecuteOnce
0x180008754  mov     r8d, 0C0000002h; unsigned int
0x18000875a  lea     rcx, [rbp+57h+var_60]; this
0x18000875e  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, 0; bool g_isPerUserCatalogEnabled
0x180008765  mov     edx, 4
0x18000876a  jnz     short loc_180008771
0x18000876c  mov     edx, 1; unsigned __int16
0x180008771  call    ?ReportEventW@ProfNotifEventLog@@QEAAJGKHPEAX0K@Z; ProfNotifEventLog::ReportEventW(ushort,ulong,int,void *,void *,ulong)
0x180008776  nop
0x180008777  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18000877b  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180008780  nop
0x180008781  lea     rcx, [rbp+57h+var_60]; this
0x180008785  call    ??1CEventLog@@QEAA@XZ; CEventLog::~CEventLog(void)
0x18000878a  lea     r11, [rsp+0B0h+var_s0]
0x180008792  mov     rbx, [r11+20h]
0x180008796  mov     rdi, [r11+28h]
0x18000879a  mov     rsp, r11
0x18000879d  pop     rbp
0x18000879e  retn
```
