# SM_CLUSTER::SM_CLUSTER(void)

- ea: `0x1400038dc`
- end: `0x140003978`
- name: `??0SM_CLUSTER@@QEAA@XZ`
- size: `156`
- prototype: `SM_CLUSTER *__fastcall(SM_CLUSTER *this, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002c1c`
- `0x140002f20`
- `0x140003190`
- `0x1400032b0`
- `0x140003494`

## callees

- `0x140001008`
- `0x1400038dc`

## pseudocode

```c
SM_CLUSTER *__fastcall SM_CLUSTER::SM_CLUSTER(SM_CLUSTER *this, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // [rsp+40h] [rbp+8h] BYREF
  const char *v7; // [rsp+48h] [rbp+10h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v6 = 36;
    v7 = "SM_CLUSTER::SM_CLUSTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&word_140010E26,
      a3,
      a4,
      (const unsigned __int16 **)&v7,
      (__int64)&v6);
  }
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( (unsigned int)dword_140014048 > 5 )
  {
    v6 = 42;
    v7 = "SM_CLUSTER::SM_CLUSTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&dword_140010F44,
      a3,
      a4,
      (const unsigned __int16 **)&v7,
      (__int64)&v6);
  }
  return this;
}

```

## disassembly

```asm
0x1400038dc  mov     r11, rsp
0x1400038df  mov     [r11+18h], rbx
0x1400038e3  push    rdi
0x1400038e4  sub     rsp, 30h
0x1400038e8  mov     eax, cs:dword_140014048
0x1400038ee  lea     rdi, aSmClusterSmClu; "SM_CLUSTER::SM_CLUSTER"
0x1400038f5  mov     rbx, rcx
0x1400038f8  cmp     eax, 5
0x1400038fb  jbe     short loc_140003925
0x1400038fd  lea     rax, [r11+8]
0x140003901  mov     [rsp+38h+arg_0], 24h ; '$'
0x140003909  mov     [r11-10h], rax
0x14000390d  lea     rdx, word_140010E26
0x140003914  lea     rax, [r11+10h]
0x140003918  mov     [r11+10h], rdi
0x14000391c  mov     [r11-18h], rax
0x140003920  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003925  xor     eax, eax
0x140003927  mov     [rbx], rax
0x14000392a  mov     [rbx+8], rax
0x14000392e  mov     [rbx+10h], rax
0x140003932  mov     eax, cs:dword_140014048
0x140003938  cmp     eax, 5
0x14000393b  jbe     short loc_14000396A
0x14000393d  lea     rax, [rsp+38h+arg_0]
0x140003942  mov     [rsp+38h+arg_0], 2Ah ; '*'
0x14000394a  mov     [rsp+38h+var_10], rax
0x14000394f  lea     rdx, dword_140010F44
0x140003956  lea     rax, [rsp+38h+arg_8]
0x14000395b  mov     [rsp+38h+arg_8], rdi
0x140003960  mov     [rsp+38h+var_18], rax
0x140003965  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000396a  mov     rax, rbx
0x14000396d  mov     rbx, [rsp+38h+arg_10]
0x140003972  add     rsp, 30h
0x140003976  pop     rdi
0x140003977  retn
```
