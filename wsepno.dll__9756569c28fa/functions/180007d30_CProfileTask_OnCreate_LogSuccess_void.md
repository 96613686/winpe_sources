# CProfileTask_OnCreate::LogSuccess(void)

- ea: `0x180007d30`
- end: `0x180007dd8`
- name: `?LogSuccess@CProfileTask_OnCreate@@UEAAXXZ`
- size: `168`
- prototype: `void __fastcall(CProfileTask_OnCreate *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800021f4`
- `0x180003be0`
- `0x180007768`
- `0x18000c200`
- `0x18000c234`
- `0x18000c374`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CProfileTask_OnCreate::LogSuccess(const wchar_t **this)
{
  int v2; // eax
  const wchar_t *v3; // rdx
  void *v4; // rdx
  __int64 v5; // [rsp+40h] [rbp-68h] BYREF
  int v6; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v7[64]; // [rsp+50h] [rbp-58h] BYREF
  int v8; // [rsp+90h] [rbp-18h]
  void *lpMem; // [rsp+B0h] [rbp+8h] BYREF

  v5 = 0;
  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  v8 = 0;
  lpMem = 0;
  v2 = CAccountDisplayString::Initialize((wchar_t **)&lpMem, this[1]);
  v3 = &qword_180011360;
  if ( v2 >= 0 )
    v3 = (const wchar_t *)lpMem;
  CEventLog::CStrArray::Append((CEventLog::CStrArray *)&v6, v3);
  ProfNotifEventLog::ReportEventW((ProfNotifEventLog *)&v5, 4u, 0x40000005u);
  ProfNotif_HeapFree(lpMem, v4);
  CEventLog::~CEventLog((CEventLog *)&v5);
}

```

## disassembly

```asm
0x180007d30  push    rbx
0x180007d32  sub     rsp, 0A0h
0x180007d39  mov     rbx, rcx
0x180007d3c  mov     [rsp+0A8h+var_68], 0
0x180007d45  mov     [rsp+0A8h+var_60], 0
0x180007d4d  xor     edx, edx; Val
0x180007d4f  lea     r8d, [rdx+40h]; Size
0x180007d53  lea     rcx, [rsp+0A8h+var_58]; void *
0x180007d58  call    memset_0
0x180007d5d  mov     [rsp+0A8h+var_18], 0
0x180007d68  mov     [rsp+0A8h+lpMem], 0
0x180007d74  mov     rdx, [rbx+8]; wchar_t *
0x180007d78  lea     rcx, [rsp+0A8h+lpMem]; this
0x180007d80  call    ?Initialize@CAccountDisplayString@@QEAAJPEB_W@Z; CAccountDisplayString::Initialize(wchar_t const *)
0x180007d85  lea     rdx, qword_180011360
0x180007d8c  test    eax, eax
0x180007d8e  cmovns  rdx, [rsp+0A8h+lpMem]; wchar_t *
0x180007d97  lea     rcx, [rsp+0A8h+var_60]; this
0x180007d9c  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x180007da1  mov     edx, 4; unsigned __int16
0x180007da6  mov     r8d, 40000005h; unsigned int
0x180007dac  lea     rcx, [rsp+0A8h+var_68]; this
0x180007db1  call    ?ReportEventW@ProfNotifEventLog@@QEAAJGKHPEAX0K@Z; ProfNotifEventLog::ReportEventW(ushort,ulong,int,void *,void *,ulong)
0x180007db6  nop
0x180007db7  mov     rcx, [rsp+0A8h+lpMem]; lpMem
0x180007dbf  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180007dc4  nop
0x180007dc5  lea     rcx, [rsp+0A8h+var_68]; this
0x180007dca  call    ??1CEventLog@@QEAA@XZ; CEventLog::~CEventLog(void)
0x180007dcf  add     rsp, 0A0h
0x180007dd6  pop     rbx
0x180007dd7  retn
```
