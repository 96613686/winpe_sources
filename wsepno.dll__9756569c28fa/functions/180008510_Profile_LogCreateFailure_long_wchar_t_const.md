# Profile_LogCreateFailure(long,wchar_t const *)

- ea: `0x180008510`
- end: `0x18000863f`
- name: `?Profile_LogCreateFailure@@YAXJPEB_W@Z`
- size: `303`
- prototype: `void __fastcall(DWORD dwMessageId, const wchar_t *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800079d0`
- `0x180007fd0`

## callees

- `0x1800021f4`
- `0x180003be0`
- `0x180007768`
- `0x180008510`
- `0x18000890c`
- `0x18000c200`
- `0x18000c234`
- `0x18000c374`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800085bc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800085bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Profile_LogCreateFailure(DWORD dwMessageId, const wchar_t *a2)
{
  int v4; // eax
  const wchar_t *v5; // rdx
  signed int LastError; // eax
  wchar_t *v7; // rbx
  void *v8; // rdx
  void *v9; // rdx
  void *lpMem; // [rsp+40h] [rbp-19h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v12; // [rsp+50h] [rbp-9h] BYREF
  int v13; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp+7h] BYREF
  int v15; // [rsp+A0h] [rbp+47h]

  v12 = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  v15 = 0;
  lpMem = 0;
  v4 = CAccountDisplayString::Initialize((wchar_t **)&lpMem, a2);
  v5 = &qword_180011360;
  if ( v4 >= 0 )
    v5 = (const wchar_t *)lpMem;
  CEventLog::CStrArray::Append((CEventLog::CStrArray *)&v13, v5);
  ProfNotifEventLog::Push(&v12, dwMessageId, 1);
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
    CEventLog::CStrArray::Append((CEventLog::CStrArray *)&v13, v7);
    ProfNotif_HeapFree(v7, v8);
  }
  ProfNotifEventLog::ReportEventW((ProfNotifEventLog *)&v12, 1u, 0xC0000006);
  ProfNotif_HeapFree(lpMem, v9);
  CEventLog::~CEventLog((CEventLog *)&v12);
}

```

## disassembly

```asm
0x180008510  mov     [rsp-8+arg_10], rbx
0x180008515  mov     [rsp-8+arg_18], rdi
0x18000851a  push    rbp
0x18000851b  lea     rbp, [rsp-57h]
0x180008520  sub     rsp, 0B0h
0x180008527  mov     rbx, rdx
0x18000852a  mov     edi, ecx
0x18000852c  mov     [rbp+57h+var_60], 0
0x180008534  mov     [rbp+57h+var_58], 0
0x18000853b  xor     edx, edx; Val
0x18000853d  lea     r8d, [rdx+40h]; Size
0x180008541  lea     rcx, [rbp+57h+var_50]; void *
0x180008545  call    memset_0
0x18000854a  mov     [rbp+57h+var_10], 0
0x180008551  mov     [rbp+57h+lpMem], 0
0x180008559  mov     rdx, rbx; wchar_t *
0x18000855c  lea     rcx, [rbp+57h+lpMem]; this
0x180008560  call    ?Initialize@CAccountDisplayString@@QEAAJPEB_W@Z; CAccountDisplayString::Initialize(wchar_t const *)
0x180008565  lea     rdx, qword_180011360
0x18000856c  test    eax, eax
0x18000856e  cmovns  rdx, [rbp+57h+lpMem]; wchar_t *
0x180008573  lea     rcx, [rbp+57h+var_58]; this
0x180008577  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x18000857c  mov     r8d, 1
0x180008582  mov     edx, edi
0x180008584  lea     rcx, [rbp+57h+var_60]
0x180008588  call    ?Push@ProfNotifEventLog@@QEAAJJW4eFmt@CEventLog@@@Z; ProfNotifEventLog::Push(long,CEventLog::eFmt)
0x18000858d  mov     qword ptr [rbp+57h+Buffer], 0
0x180008595  mov     [rsp+0B0h+Arguments], 0; unsigned int
0x18000859e  mov     [rsp+0B0h+nSize], 1; void *
0x1800085a6  lea     rax, [rbp+57h+Buffer]
0x1800085aa  mov     [rsp+0B0h+lpBuffer], rax; void *
0x1800085af  xor     r9d, r9d; dwLanguageId
0x1800085b2  mov     r8d, edi; dwMessageId
0x1800085b5  xor     edx, edx; lpSource
0x1800085b7  mov     ecx, 1100h; dwFlags
0x1800085bc  call    cs:__imp_FormatMessageW
0x1800085c2  test    eax, eax
0x1800085c4  jnz     short loc_1800085E0
0x1800085c6  call    cs:__imp_GetLastError
0x1800085cc  test    eax, eax
0x1800085ce  jle     short loc_1800085D8
0x1800085d0  movzx   eax, ax
0x1800085d3  or      eax, 80070000h
0x1800085d8  xor     ebx, ebx
0x1800085da  test    eax, eax
0x1800085dc  js      short loc_180008602
0x1800085de  jmp     short loc_1800085EE
0x1800085e0  xor     ebx, ebx
0x1800085e2  mov     rax, qword ptr [rbp+57h+Buffer]
0x1800085e6  test    rax, rax
0x1800085e9  jz      short loc_1800085EE
0x1800085eb  mov     rbx, rax
0x1800085ee  mov     rdx, rbx; wchar_t *
0x1800085f1  lea     rcx, [rbp+57h+var_58]; this
0x1800085f5  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x1800085fa  mov     rcx, rbx; lpMem
0x1800085fd  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180008602  mov     edx, 1; unsigned __int16
0x180008607  mov     r8d, 0C0000006h; unsigned int
0x18000860d  lea     rcx, [rbp+57h+var_60]; this
0x180008611  call    ?ReportEventW@ProfNotifEventLog@@QEAAJGKHPEAX0K@Z; ProfNotifEventLog::ReportEventW(ushort,ulong,int,void *,void *,ulong)
0x180008616  nop
0x180008617  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18000861b  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180008620  nop
0x180008621  lea     rcx, [rbp+57h+var_60]; this
0x180008625  call    ??1CEventLog@@QEAA@XZ; CEventLog::~CEventLog(void)
0x18000862a  lea     r11, [rsp+0B0h+var_s0]
0x180008632  mov     rbx, [r11+20h]
0x180008636  mov     rdi, [r11+28h]
0x18000863a  mov     rsp, r11
0x18000863d  pop     rbp
0x18000863e  retn
```
