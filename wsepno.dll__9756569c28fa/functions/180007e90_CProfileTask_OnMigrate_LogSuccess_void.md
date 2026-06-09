# CProfileTask_OnMigrate::LogSuccess(void)

- ea: `0x180007e90`
- end: `0x180007f6b`
- name: `?LogSuccess@CProfileTask_OnMigrate@@UEAAXXZ`
- size: `219`
- prototype: `void __fastcall(CProfileTask_OnMigrate *__hidden this)`
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
// Hidden C++ exception states: #wind=3
void __fastcall CProfileTask_OnMigrate::LogSuccess(const wchar_t **this)
{
  const wchar_t *v2; // rsi
  wchar_t *v3; // rbx
  void *v4; // rdx
  void *v5; // rdx
  __int64 v6; // [rsp+40h] [rbp-19h] BYREF
  int v7; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v8[64]; // [rsp+50h] [rbp-9h] BYREF
  int v9; // [rsp+90h] [rbp+37h]
  void *lpMem; // [rsp+C0h] [rbp+67h] BYREF
  wchar_t *v11; // [rsp+C8h] [rbp+6Fh] BYREF

  v6 = 0;
  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  v9 = 0;
  v2 = &qword_180011360;
  v11 = 0;
  lpMem = 0;
  v3 = (wchar_t *)&qword_180011360;
  if ( (int)CAccountDisplayString::Initialize(&v11, this[1]) >= 0 )
    v3 = v11;
  if ( (int)CAccountDisplayString::Initialize((wchar_t **)&lpMem, this[2]) >= 0 )
    v2 = (const wchar_t *)lpMem;
  CEventLog::CStrArray::Append((CEventLog::CStrArray *)&v7, v3);
  CEventLog::CStrArray::Append((CEventLog::CStrArray *)&v7, v2);
  ProfNotifEventLog::ReportEventW((ProfNotifEventLog *)&v6, 4u, 0x40000003u);
  ProfNotif_HeapFree(lpMem, v4);
  ProfNotif_HeapFree(v11, v5);
  CEventLog::~CEventLog((CEventLog *)&v6);
}

```

## disassembly

```asm
0x180007e90  mov     [rsp-8+arg_10], rbx
0x180007e95  push    rbp
0x180007e96  push    rsi
0x180007e97  push    rdi
0x180007e98  lea     rbp, [rsp-47h]
0x180007e9d  sub     rsp, 0A0h
0x180007ea4  mov     rdi, rcx
0x180007ea7  mov     [rbp+57h+var_70], 0
0x180007eaf  mov     [rbp+57h+var_68], 0
0x180007eb6  xor     edx, edx; Val
0x180007eb8  lea     r8d, [rdx+40h]; Size
0x180007ebc  lea     rcx, [rbp+57h+var_60]; void *
0x180007ec0  call    memset_0
0x180007ec5  mov     [rbp+57h+var_20], 0
0x180007ecc  lea     rsi, qword_180011360
0x180007ed3  mov     [rbp+57h+arg_8], 0
0x180007edb  mov     [rbp+57h+lpMem], 0
0x180007ee3  mov     rdx, [rdi+8]; wchar_t *
0x180007ee7  lea     rcx, [rbp+57h+arg_8]; this
0x180007eeb  call    ?Initialize@CAccountDisplayString@@QEAAJPEB_W@Z; CAccountDisplayString::Initialize(wchar_t const *)
0x180007ef0  mov     rbx, rsi
0x180007ef3  test    eax, eax
0x180007ef5  cmovns  rbx, [rbp+57h+arg_8]
0x180007efa  mov     rdx, [rdi+10h]; wchar_t *
0x180007efe  lea     rcx, [rbp+57h+lpMem]; this
0x180007f02  call    ?Initialize@CAccountDisplayString@@QEAAJPEB_W@Z; CAccountDisplayString::Initialize(wchar_t const *)
0x180007f07  test    eax, eax
0x180007f09  cmovns  rsi, [rbp+57h+lpMem]
0x180007f0e  mov     rdx, rbx; wchar_t *
0x180007f11  lea     rcx, [rbp+57h+var_68]; this
0x180007f15  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x180007f1a  mov     rdx, rsi; wchar_t *
0x180007f1d  lea     rcx, [rbp+57h+var_68]; this
0x180007f21  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x180007f26  mov     edx, 4; unsigned __int16
0x180007f2b  mov     r8d, 40000003h; unsigned int
0x180007f31  lea     rcx, [rbp+57h+var_70]; this
0x180007f35  call    ?ReportEventW@ProfNotifEventLog@@QEAAJGKHPEAX0K@Z; ProfNotifEventLog::ReportEventW(ushort,ulong,int,void *,void *,ulong)
0x180007f3a  nop
0x180007f3b  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180007f3f  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180007f44  nop
0x180007f45  mov     rcx, [rbp+57h+arg_8]; lpMem
0x180007f49  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180007f4e  nop
0x180007f4f  lea     rcx, [rbp+57h+var_70]; this
0x180007f53  call    ??1CEventLog@@QEAA@XZ; CEventLog::~CEventLog(void)
0x180007f58  mov     rbx, [rsp+0B0h+arg_10]
0x180007f60  add     rsp, 0A0h
0x180007f67  pop     rdi
0x180007f68  pop     rsi
0x180007f69  pop     rbp
0x180007f6a  retn
```
