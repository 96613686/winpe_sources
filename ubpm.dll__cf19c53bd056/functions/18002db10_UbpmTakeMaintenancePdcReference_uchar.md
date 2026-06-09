# UbpmTakeMaintenancePdcReference(uchar)

- ea: `0x18002db10`
- end: `0x18002dbe1`
- name: `?UbpmTakeMaintenancePdcReference@@YAXE@Z`
- size: `209`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002ea04`
- `0x18002eb98`
- `0x18002ef50`

## callees

- `0x180024550`
- `0x1800270c8`
- `0x18002db10`

## import_xrefs

- `UMPDC!PdcActivationClientActivityRequest` at `0x18002db3f`
- `UMPDC!PdcActivationClientActivityRequest` at `0x18002db3f`
- `UMPDC!PdcTaskClientRequest` at `0x18002db49`
- `UMPDC!PdcTaskClientRequest` at `0x18002db49`

## pseudocode

```c
void __fastcall UbpmTakeMaintenancePdcReference(char a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  int v5; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // [rsp+50h] [rbp-18h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h] BYREF
  char v11; // [rsp+78h] [rbp+10h] BYREF
  char v12; // [rsp+80h] [rbp+18h] BYREF
  int v13; // [rsp+88h] [rbp+20h] BYREF

  if ( !qword_18004CB38 || byte_18004CB40 == a1 )
    goto LABEL_9;
  v4 = (unsigned int)(dword_18004CB34 - 1);
  if ( dword_18004CB34 == 1 )
  {
    LOBYTE(v4) = a1;
    v5 = PdcTaskClientRequest(qword_18004CB38, v4);
  }
  else
  {
    if ( dword_18004CB34 != 2 )
      goto LABEL_9;
    LOBYTE(a3) = a1;
    v5 = PdcActivationClientActivityRequest(qword_18004CB38, v4, a3);
  }
  if ( v5 >= 0 )
    byte_18004CB40 = a1;
LABEL_9:
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v11 = byte_18004CB40;
    v10 = qword_18004CB38;
    v13 = dword_18004CB34;
    v9 = UbpmpMaintenanceTotalTasksRunning();
    v12 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
      v6,
      (unsigned int)&unk_1800440D0,
      v7,
      v8,
      (__int64)&v12,
      (__int64)&v9,
      (__int64)&v13,
      (__int64)&v10,
      (__int64)&v11);
  }
}

```

## disassembly

```asm
0x18002db10  push    rbx
0x18002db12  sub     rsp, 60h
0x18002db16  mov     bl, cl
0x18002db18  mov     rcx, cs:qword_18004CB38
0x18002db1f  test    rcx, rcx
0x18002db22  jz      short loc_18002DB59
0x18002db24  cmp     cs:byte_18004CB40, bl
0x18002db2a  jz      short loc_18002DB59
0x18002db2c  mov     edx, cs:dword_18004CB34
0x18002db32  sub     edx, 1
0x18002db35  jz      short loc_18002DB47
0x18002db37  cmp     edx, 1
0x18002db3a  jnz     short loc_18002DB59
0x18002db3c  mov     r8b, bl
0x18002db3f  call    cs:__imp_PdcActivationClientActivityRequest
0x18002db45  jmp     short loc_18002DB4F
0x18002db47  mov     dl, bl
0x18002db49  call    cs:__imp_PdcTaskClientRequest
0x18002db4f  test    eax, eax
0x18002db51  js      short loc_18002DB59
0x18002db53  mov     cs:byte_18004CB40, bl
0x18002db59  mov     eax, cs:dword_18004C0F0
0x18002db5f  cmp     eax, 4
0x18002db62  jbe     short loc_18002DBDB
0x18002db64  mov     al, cs:byte_18004CB40
0x18002db6a  mov     [rsp+68h+arg_8], al
0x18002db6e  mov     rax, cs:qword_18004CB38
0x18002db75  mov     [rsp+68h+var_10], rax
0x18002db7a  mov     eax, cs:dword_18004CB34
0x18002db80  mov     [rsp+68h+arg_18], eax
0x18002db87  call    ?UbpmpMaintenanceTotalTasksRunning@@YAKXZ; UbpmpMaintenanceTotalTasksRunning(void)
0x18002db8c  mov     [rsp+68h+var_18], eax
0x18002db90  lea     rdx, unk_1800440D0
0x18002db97  lea     rax, [rsp+68h+arg_8]
0x18002db9c  mov     [rsp+68h+arg_10], bl
0x18002dba3  mov     [rsp+68h+var_28], rax
0x18002dba8  lea     rax, [rsp+68h+var_10]
0x18002dbad  mov     [rsp+68h+var_30], rax
0x18002dbb2  lea     rax, [rsp+68h+arg_18]
0x18002dbba  mov     [rsp+68h+var_38], rax
0x18002dbbf  lea     rax, [rsp+68h+var_18]
0x18002dbc4  mov     [rsp+68h+var_40], rax
0x18002dbc9  lea     rax, [rsp+68h+arg_10]
0x18002dbd1  mov     [rsp+68h+var_48], rax
0x18002dbd6  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &)
0x18002dbdb  add     rsp, 60h
0x18002dbdf  pop     rbx
0x18002dbe0  retn
```
