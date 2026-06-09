# SmExecuteWorkRemote(_SU_WORK_OBJECT *,_GUID *)

- ea: `0x140003494`
- end: `0x140003617`
- name: `?SmExecuteWorkRemote@@YAHPEAU_SU_WORK_OBJECT@@PEAU_GUID@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(struct _SU_WORK_OBJECT *, struct _GUID *, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140002230`
- `0x140003190`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x140003494`
- `0x1400038dc`
- `0x140003980`
- `0x140003b54`
- `0x140003c80`
- `0x140003de0`
- `0x14000913c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000353f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000353f`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x1400035d0`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x1400035d0`

## pseudocode

```c
__int64 __fastcall SmExecuteWorkRemote(struct _SU_WORK_OBJECT *a1, struct _GUID *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // r8d
  int v12; // r9d
  struct _HRESOURCE *v13; // rax
  SM_CLUSTER *v14; // rcx
  struct _HRESOURCE *v15; // rsi
  DWORD LastError; // eax
  const char *v18; // [rsp+40h] [rbp-20h] BYREF
  HCLUSTER v19[3]; // [rsp+48h] [rbp-18h] BYREF
  int v20; // [rsp+90h] [rbp+30h] BYREF
  const char *v21; // [rsp+98h] [rbp+38h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v20 = 358;
    v21 = "SmExecuteWorkRemote";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)byte_1400107B3,
      a3,
      a4,
      (const unsigned __int16 **)&v21,
      (__int64)&v20);
  }
  SM_CLUSTER::SM_CLUSTER((SM_CLUSTER *)v19, (__int64)a2, a3, a4);
  v8 = SuExecuteWork(a1);
  if ( !v8 )
    goto LABEL_8;
  if ( *((_DWORD *)a1 + 35) == 15138819 )
  {
    *((_DWORD *)a1 + 36) = 0;
    v8 = SM_CLUSTER::Initialize((SM_CLUSTER *)v19, v6, v9, v10);
    if ( !v8 )
      goto LABEL_8;
    v13 = SM_CLUSTER::OpenResourceById(v19, a2, v11, v12);
    v15 = v13;
    if ( !v13 )
    {
      v8 = 0;
LABEL_8:
      LastError = GetLastError();
      if ( (unsigned int)dword_140014048 > 2 )
      {
        v20 = LastError;
        LODWORD(v21) = 415;
        v18 = "SmExecuteWorkRemote";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_140014048,
          (__int64)qword_1400105D8,
          v9,
          v10,
          (const unsigned __int16 **)&v18,
          (__int64)&v21,
          (__int64)&v20);
      }
      goto LABEL_10;
    }
    v8 = SM_CLUSTER::SendWork(v14, v13, a1, *((_DWORD *)a1 + 14) + 52);
    if ( v8 && *((_DWORD *)a1 + 35) == 15138819 )
      v8 = 0;
    CloseClusterResource(v15);
    if ( !v8 )
      goto LABEL_8;
  }
  if ( (unsigned int)dword_140014048 > 5 )
  {
    v20 = 415;
    v21 = "SmExecuteWorkRemote";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (__int64)byte_140010AA5,
      v9,
      v10,
      (const unsigned __int16 **)&v21,
      (__int64)&v20);
  }
LABEL_10:
  SM_CLUSTER::~SM_CLUSTER((SM_CLUSTER *)v19, v6, v9, v10);
  return v8;
}

```

## disassembly

```asm
0x140003494  mov     r11, rsp
0x140003497  mov     [r11+8], rbx
0x14000349b  mov     [r11+10h], rsi
0x14000349f  push    rbp
0x1400034a0  push    rdi
0x1400034a1  push    r14
0x1400034a3  mov     rbp, rsp
0x1400034a6  sub     rsp, 60h
0x1400034aa  mov     eax, cs:dword_140014048
0x1400034b0  lea     r14, aSmexecuteworkr; "SmExecuteWorkRemote"
0x1400034b7  mov     rsi, rdx
0x1400034ba  mov     rdi, rcx
0x1400034bd  cmp     eax, 5
0x1400034c0  jbe     short loc_1400034E9
0x1400034c2  lea     rax, [rbp+arg_10]
0x1400034c6  mov     [rbp+arg_10], 166h
0x1400034cd  mov     [r11-50h], rax
0x1400034d1  lea     rdx, byte_1400107B3
0x1400034d8  lea     rax, [rbp+arg_18]
0x1400034dc  mov     [rbp+arg_18], r14
0x1400034e0  mov     [r11-58h], rax
0x1400034e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400034e9  lea     rcx, [rbp+var_18]; this
0x1400034ed  call    ??0SM_CLUSTER@@QEAA@XZ; SM_CLUSTER::SM_CLUSTER(void)
0x1400034f2  mov     rcx, rdi; struct _SU_WORK_OBJECT *
0x1400034f5  call    ?SuExecuteWork@@YAHPEAU_SU_WORK_OBJECT@@@Z; SuExecuteWork(_SU_WORK_OBJECT *)
0x1400034fa  mov     ebx, eax
0x1400034fc  test    eax, eax
0x1400034fe  jz      short loc_14000353F
0x140003500  cmp     dword ptr [rdi+8Ch], 0E70003h
0x14000350a  jnz     loc_1400035DE
0x140003510  lea     rcx, [rbp+var_18]; this
0x140003514  mov     dword ptr [rdi+90h], 0
0x14000351e  call    ?Initialize@SM_CLUSTER@@QEAAHXZ; SM_CLUSTER::Initialize(void)
0x140003523  mov     ebx, eax
0x140003525  test    eax, eax
0x140003527  jz      short loc_14000353F
0x140003529  mov     rdx, rsi; struct _GUID *
0x14000352c  lea     rcx, [rbp+var_18]; this
0x140003530  call    ?OpenResourceById@SM_CLUSTER@@QEAAPEAU_HRESOURCE@@PEAU_GUID@@@Z; SM_CLUSTER::OpenResourceById(_GUID *)
0x140003535  mov     rsi, rax
0x140003538  test    rax, rax
0x14000353b  jnz     short loc_1400035A5
0x14000353d  xor     ebx, ebx
0x14000353f  call    cs:__imp_GetLastError
0x140003545  mov     ecx, cs:dword_140014048
0x14000354b  cmp     ecx, 2
0x14000354e  jbe     short loc_140003585
0x140003550  mov     [rbp+arg_10], eax
0x140003553  lea     rdx, qword_1400105D8
0x14000355a  lea     rax, [rbp+arg_10]
0x14000355e  mov     dword ptr [rbp+arg_18], 19Fh
0x140003565  mov     [rsp+60h+var_30], rax
0x14000356a  lea     rax, [rbp+arg_18]
0x14000356e  mov     [rsp+60h+var_38], rax
0x140003573  lea     rax, [rbp+var_20]
0x140003577  mov     [rsp+60h+var_40], rax
0x14000357c  mov     [rbp+var_20], r14
0x140003580  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003585  lea     rcx, [rbp+var_18]; this
0x140003589  call    ??1SM_CLUSTER@@QEAA@XZ; SM_CLUSTER::~SM_CLUSTER(void)
0x14000358e  lea     r11, [rsp+60h+var_s0]
0x140003593  mov     eax, ebx
0x140003595  mov     rbx, [r11+20h]
0x140003599  mov     rsi, [r11+28h]
0x14000359d  mov     rsp, r11
0x1400035a0  pop     r14
0x1400035a2  pop     rdi
0x1400035a3  pop     rbp
0x1400035a4  retn
0x1400035a5  mov     r9d, [rdi+38h]
0x1400035a9  mov     r8, rdi; void *
0x1400035ac  add     r9d, 34h ; '4'; unsigned int
0x1400035b0  mov     rdx, rsi; struct _HRESOURCE *
0x1400035b3  call    ?SendWork@SM_CLUSTER@@QEAAHPEAU_HRESOURCE@@PEAXK@Z; SM_CLUSTER::SendWork(_HRESOURCE *,void *,ulong)
0x1400035b8  mov     ebx, eax
0x1400035ba  test    eax, eax
0x1400035bc  jz      short loc_1400035CD
0x1400035be  xor     eax, eax
0x1400035c0  cmp     dword ptr [rdi+8Ch], 0E70003h
0x1400035ca  cmovz   ebx, eax
0x1400035cd  mov     rcx, rsi; hResource
0x1400035d0  call    cs:__imp_CloseClusterResource
0x1400035d6  test    ebx, ebx
0x1400035d8  jz      loc_14000353F
0x1400035de  mov     eax, cs:dword_140014048
0x1400035e4  cmp     eax, 5
0x1400035e7  jbe     short loc_140003585
0x1400035e9  lea     rax, [rbp+arg_10]
0x1400035ed  mov     [rbp+arg_10], 19Fh
0x1400035f4  mov     [rsp+60h+var_38], rax
0x1400035f9  lea     rdx, byte_140010AA5
0x140003600  lea     rax, [rbp+arg_18]
0x140003604  mov     [rbp+arg_18], r14
0x140003608  mov     [rsp+60h+var_40], rax
0x14000360d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003612  jmp     loc_140003585
```
