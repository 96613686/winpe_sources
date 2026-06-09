# CProfileTask_OnDelete::LogSuccess(void)

- ea: `0x180007de0`
- end: `0x180007e88`
- name: `?LogSuccess@CProfileTask_OnDelete@@UEAAXXZ`
- size: `168`
- prototype: `void __fastcall(CProfileTask_OnDelete *__hidden this)`
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
void __fastcall CProfileTask_OnDelete::LogSuccess(const wchar_t **this)
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
  v2 = CAccountDisplayString::Initialize((wchar_t **)&lpMem, this[2]);
  v3 = &qword_180011360;
  if ( v2 >= 0 )
    v3 = (const wchar_t *)lpMem;
  CEventLog::CStrArray::Append((CEventLog::CStrArray *)&v6, v3);
  ProfNotifEventLog::ReportEventW((ProfNotifEventLog *)&v5, 4u, 0x40000001u);
  ProfNotif_HeapFree(lpMem, v4);
  CEventLog::~CEventLog((CEventLog *)&v5);
}

```

## disassembly

```asm
0x180007de0  push    rbx
0x180007de2  sub     rsp, 0A0h
0x180007de9  mov     rbx, rcx
0x180007dec  mov     [rsp+0A8h+var_68], 0
0x180007df5  mov     [rsp+0A8h+var_60], 0
0x180007dfd  xor     edx, edx; Val
0x180007dff  lea     r8d, [rdx+40h]; Size
0x180007e03  lea     rcx, [rsp+0A8h+var_58]; void *
0x180007e08  call    memset_0
0x180007e0d  mov     [rsp+0A8h+var_18], 0
0x180007e18  mov     [rsp+0A8h+lpMem], 0
0x180007e24  mov     rdx, [rbx+10h]; wchar_t *
0x180007e28  lea     rcx, [rsp+0A8h+lpMem]; this
0x180007e30  call    ?Initialize@CAccountDisplayString@@QEAAJPEB_W@Z; CAccountDisplayString::Initialize(wchar_t const *)
0x180007e35  lea     rdx, qword_180011360
0x180007e3c  test    eax, eax
0x180007e3e  cmovns  rdx, [rsp+0A8h+lpMem]; wchar_t *
0x180007e47  lea     rcx, [rsp+0A8h+var_60]; this
0x180007e4c  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x180007e51  mov     edx, 4; unsigned __int16
0x180007e56  mov     r8d, 40000001h; unsigned int
0x180007e5c  lea     rcx, [rsp+0A8h+var_68]; this
0x180007e61  call    ?ReportEventW@ProfNotifEventLog@@QEAAJGKHPEAX0K@Z; ProfNotifEventLog::ReportEventW(ushort,ulong,int,void *,void *,ulong)
0x180007e66  nop
0x180007e67  mov     rcx, [rsp+0A8h+lpMem]; lpMem
0x180007e6f  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180007e74  nop
0x180007e75  lea     rcx, [rsp+0A8h+var_68]; this
0x180007e7a  call    ??1CEventLog@@QEAA@XZ; CEventLog::~CEventLog(void)
0x180007e7f  add     rsp, 0A0h
0x180007e86  pop     rbx
0x180007e87  retn
```
