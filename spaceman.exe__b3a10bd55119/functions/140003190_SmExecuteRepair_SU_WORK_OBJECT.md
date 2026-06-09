# SmExecuteRepair(_SU_WORK_OBJECT *)

- ea: `0x140003190`
- end: `0x1400032a9`
- name: `?SmExecuteRepair@@YAHPEAU_SU_WORK_OBJECT@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(struct _SU_WORK_OBJECT *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140002230`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x140003190`
- `0x140003494`
- `0x1400038dc`
- `0x140003980`
- `0x14000913c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003212`

## string_xrefs

- `0x1400031a5`: `SmExecuteRepair`

## pseudocode

```c
__int64 __fastcall SmExecuteRepair(struct _SU_WORK_OBJECT *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD LastError; // eax
  _BYTE v12[32]; // [rsp+40h] [rbp-20h] BYREF
  int v13; // [rsp+88h] [rbp+28h] BYREF
  const char *v14; // [rsp+90h] [rbp+30h] BYREF
  const char *v15; // [rsp+98h] [rbp+38h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v13 = 426;
    v14 = "SmExecuteRepair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)byte_14001069B,
      a3,
      a4,
      (const unsigned __int16 **)&v14,
      (__int64)&v13);
  }
  SM_CLUSTER::SM_CLUSTER((SM_CLUSTER *)v12, a2, a3, a4);
  v7 = SuExecuteWork(a1);
  if ( v7 )
  {
    if ( *((_DWORD *)a1 + 35) != 15138819 )
      goto LABEL_9;
    v7 = SmExecuteWorkRemote(a1, (struct _GUID *)((char *)a1 + 68));
  }
  if ( !v7 )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_140014048 > 2 )
    {
      v13 = LastError;
      LODWORD(v14) = 452;
      v15 = "SmExecuteRepair";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)dword_140014048,
        (__int64)&byte_1400108FF,
        v8,
        v9,
        (const unsigned __int16 **)&v15,
        (__int64)&v14,
        (__int64)&v13);
    }
    goto LABEL_11;
  }
LABEL_9:
  if ( (unsigned int)dword_140014048 > 5 )
  {
    v13 = 452;
    v14 = "SmExecuteRepair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)byte_140010A4B,
      v8,
      v9,
      (const unsigned __int16 **)&v14,
      (__int64)&v13);
  }
LABEL_11:
  SM_CLUSTER::~SM_CLUSTER((SM_CLUSTER *)v12, v5, v8, v9);
  return v7;
}

```

## disassembly

```asm
0x140003190  mov     [rsp-18h+arg_0], rbx
0x140003195  push    rbp
0x140003196  push    rsi
0x140003197  push    rdi
0x140003198  mov     rbp, rsp
0x14000319b  sub     rsp, 60h
0x14000319f  mov     eax, cs:dword_140014048
0x1400031a5  lea     rsi, aSmexecuterepai; "SmExecuteRepair"
0x1400031ac  mov     rdi, rcx
0x1400031af  cmp     eax, 5
0x1400031b2  jbe     short loc_1400031DD
0x1400031b4  lea     rax, [rbp+arg_8]
0x1400031b8  mov     [rbp+arg_8], 1AAh
0x1400031bf  mov     [rsp+60h+var_38], rax
0x1400031c4  lea     rdx, byte_14001069B
0x1400031cb  lea     rax, [rbp+arg_10]
0x1400031cf  mov     [rbp+arg_10], rsi
0x1400031d3  mov     [rsp+60h+var_40], rax
0x1400031d8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400031dd  lea     rcx, [rbp+var_20]; this
0x1400031e1  call    ??0SM_CLUSTER@@QEAA@XZ; SM_CLUSTER::SM_CLUSTER(void)
0x1400031e6  mov     rcx, rdi; struct _SU_WORK_OBJECT *
0x1400031e9  call    ?SuExecuteWork@@YAHPEAU_SU_WORK_OBJECT@@@Z; SuExecuteWork(_SU_WORK_OBJECT *)
0x1400031ee  mov     ebx, eax
0x1400031f0  test    eax, eax
0x1400031f2  jz      short loc_14000320E
0x1400031f4  cmp     dword ptr [rdi+8Ch], 0E70003h
0x1400031fe  jnz     short loc_14000325A
0x140003200  lea     rdx, [rdi+44h]; struct _GUID *
0x140003204  mov     rcx, rdi; struct _SU_WORK_OBJECT *
0x140003207  call    ?SmExecuteWorkRemote@@YAHPEAU_SU_WORK_OBJECT@@PEAU_GUID@@@Z; SmExecuteWorkRemote(_SU_WORK_OBJECT *,_GUID *)
0x14000320c  mov     ebx, eax
0x14000320e  test    ebx, ebx
0x140003210  jnz     short loc_14000325A
0x140003212  call    cs:__imp_GetLastError
0x140003218  mov     ecx, cs:dword_140014048
0x14000321e  cmp     ecx, 2
0x140003221  jbe     short loc_14000328E
0x140003223  mov     [rbp+arg_8], eax
0x140003226  lea     rdx, byte_1400108FF
0x14000322d  lea     rax, [rbp+arg_8]
0x140003231  mov     dword ptr [rbp+arg_10], 1C4h
0x140003238  mov     [rsp+60h+var_30], rax
0x14000323d  lea     rax, [rbp+arg_10]
0x140003241  mov     [rsp+60h+var_38], rax
0x140003246  lea     rax, [rbp+arg_18]
0x14000324a  mov     [rsp+60h+var_40], rax
0x14000324f  mov     [rbp+arg_18], rsi
0x140003253  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003258  jmp     short loc_14000328E
0x14000325a  mov     eax, cs:dword_140014048
0x140003260  cmp     eax, 5
0x140003263  jbe     short loc_14000328E
0x140003265  lea     rax, [rbp+arg_8]
0x140003269  mov     [rbp+arg_8], 1C4h
0x140003270  mov     [rsp+60h+var_38], rax
0x140003275  lea     rdx, byte_140010A4B
0x14000327c  lea     rax, [rbp+arg_10]
0x140003280  mov     [rbp+arg_10], rsi
0x140003284  mov     [rsp+60h+var_40], rax
0x140003289  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000328e  lea     rcx, [rbp+var_20]; this
0x140003292  call    ??1SM_CLUSTER@@QEAA@XZ; SM_CLUSTER::~SM_CLUSTER(void)
0x140003297  mov     eax, ebx
0x140003299  mov     rbx, [rsp+60h+arg_0]
0x1400032a1  add     rsp, 60h
0x1400032a5  pop     rdi
0x1400032a6  pop     rsi
0x1400032a7  pop     rbp
0x1400032a8  retn
```
