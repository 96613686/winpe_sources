# SM_CLUSTER::SpaceDetachExceptLocal(_SP_ID *)

- ea: `0x14000402c`
- end: `0x140004198`
- name: `?SpaceDetachExceptLocal@SM_CLUSTER@@QEAAHPEAU_SP_ID@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(SM_CLUSTER *this, struct _SP_ID *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140002c1c`
- `0x140002f20`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x14000402c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000414b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000414b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004100`
- `ext-ms-win-cluster-clusapi-l1-1-4!ClusterSendReceiveMrr` at `0x1400040b7`
- `ext-ms-win-cluster-clusapi-l1-1-4!ClusterSendReceiveMrr` at `0x1400040b7`
- `ext-ms-win-cluster-clusapi-l1-1-4!ClusterFreeMrrResponse` at `0x1400040f6`
- `ext-ms-win-cluster-clusapi-l1-1-4!ClusterFreeMrrResponse` at `0x1400040f6`

## pseudocode

```c
__int64 __fastcall SM_CLUSTER::SpaceDetachExceptLocal(SM_CLUSTER *this, struct _SP_ID *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v8; // eax
  unsigned __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdx
  DWORD LastError; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  const char *v17; // [rsp+50h] [rbp-10h] BYREF
  int v18; // [rsp+90h] [rbp+30h] BYREF
  const char *v19; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int *v20; // [rsp+A8h] [rbp+48h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v18 = 115;
    v19 = "SM_CLUSTER::SpaceDetachExceptLocal";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)byte_140010D09,
      a3,
      a4,
      (const unsigned __int16 **)&v19,
      (__int64)&v18);
  }
  v6 = *(_QWORD *)this;
  v7 = 0;
  v20 = 0;
  v8 = ClusterSendReceiveMrr(v6, 3, -1, 150000, 0, 4, 32, a2, &v20);
  v11 = (__int64)v20;
  if ( !v8 )
  {
    v9 = *v20;
    if ( *v20 )
    {
      v12 = 0;
      while ( 1 )
      {
        v10 = *(unsigned int *)(32 * v12 + *((_QWORD *)v20 + 1) + 12);
        if ( (_DWORD)v10 )
          break;
        if ( ++v12 >= v9 )
          goto LABEL_8;
      }
      SetLastError(v10);
      v11 = (__int64)v20;
    }
    else
    {
LABEL_8:
      v7 = 1;
    }
  }
  if ( v11 )
    ClusterFreeMrrResponse();
  if ( v7 )
  {
    if ( (unsigned int)dword_140014048 > 5 )
    {
      v18 = 155;
      v19 = "SM_CLUSTER::SpaceDetachExceptLocal";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v11,
        (__int64)&byte_140010D37,
        v9,
        v10,
        (const unsigned __int16 **)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_140014048 > 2 )
    {
      v18 = LastError;
      LODWORD(v19) = 155;
      v17 = "SM_CLUSTER::SpaceDetachExceptLocal";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)dword_140014048,
        (__int64)word_140010E82,
        v14,
        v15,
        (const unsigned __int16 **)&v17,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000402c  push    rbp
0x14000402e  push    rbx
0x14000402f  push    rsi
0x140004030  push    rdi
0x140004031  push    r14
0x140004033  mov     rbp, rsp
0x140004036  sub     rsp, 60h
0x14000403a  mov     eax, cs:dword_140014048
0x140004040  lea     r14, aSmClusterSpace; "SM_CLUSTER::SpaceDetachExceptLocal"
0x140004047  mov     rdi, rdx
0x14000404a  mov     rsi, rcx
0x14000404d  cmp     eax, 5
0x140004050  jbe     short loc_14000407B
0x140004052  lea     rax, [rbp+arg_0]
0x140004056  mov     [rbp+arg_0], 73h ; 's'
0x14000405d  mov     [rsp+60h+var_38], rax
0x140004062  lea     rdx, byte_140010D09
0x140004069  lea     rax, [rbp+arg_10]
0x14000406d  mov     [rbp+arg_10], r14
0x140004071  mov     [rsp+60h+var_40], rax
0x140004076  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000407b  mov     rcx, [rsi]
0x14000407e  lea     rax, [rbp+arg_18]
0x140004082  mov     [rsp+60h+var_20], rax
0x140004087  xor     ebx, ebx
0x140004089  mov     [rsp+60h+var_28], rdi
0x14000408e  mov     r9d, 249F0h
0x140004094  mov     dword ptr [rsp+60h+var_30], 20h ; ' '
0x14000409c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400040a0  mov     dword ptr [rsp+60h+var_38], 4
0x1400040a8  lea     edx, [rbx+3]
0x1400040ab  mov     dword ptr [rsp+60h+var_40], ebx
0x1400040af  mov     [rbp+arg_18], 0
0x1400040b7  call    cs:__imp_ClusterSendReceiveMrr
0x1400040bd  mov     rcx, [rbp+arg_18]
0x1400040c1  test    eax, eax
0x1400040c3  jnz     short loc_1400040F1
0x1400040c5  mov     r8d, [rcx]
0x1400040c8  test    r8, r8
0x1400040cb  jz      short loc_1400040EC
0x1400040cd  mov     r10, [rcx+8]
0x1400040d1  xor     edx, edx
0x1400040d3  mov     rax, rdx
0x1400040d6  shl     rax, 5
0x1400040da  mov     r9d, [rax+r10+0Ch]
0x1400040df  test    r9d, r9d
0x1400040e2  jnz     short loc_140004148
0x1400040e4  inc     rdx
0x1400040e7  cmp     rdx, r8
0x1400040ea  jb      short loc_1400040D3
0x1400040ec  mov     ebx, 1
0x1400040f1  test    rcx, rcx
0x1400040f4  jz      short loc_1400040FC
0x1400040f6  call    cs:__imp_ClusterFreeMrrResponse
0x1400040fc  test    ebx, ebx
0x1400040fe  jnz     short loc_140004157
0x140004100  call    cs:__imp_GetLastError
0x140004106  mov     ecx, cs:dword_140014048
0x14000410c  cmp     ecx, 2
0x14000410f  jbe     short loc_14000418B
0x140004111  mov     [rbp+arg_0], eax
0x140004114  lea     rdx, word_140010E82
0x14000411b  lea     rax, [rbp+arg_0]
0x14000411f  mov     dword ptr [rbp+arg_10], 9Bh
0x140004126  mov     [rsp+60h+var_30], rax
0x14000412b  lea     rax, [rbp+arg_10]
0x14000412f  mov     [rsp+60h+var_38], rax
0x140004134  lea     rax, [rbp+var_10]
0x140004138  mov     [rsp+60h+var_40], rax
0x14000413d  mov     [rbp+var_10], r14
0x140004141  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140004146  jmp     short loc_14000418B
0x140004148  mov     ecx, r9d; dwErrCode
0x14000414b  call    cs:__imp_SetLastError
0x140004151  mov     rcx, [rbp+arg_18]
0x140004155  jmp     short loc_1400040F1
0x140004157  mov     eax, cs:dword_140014048
0x14000415d  cmp     eax, 5
0x140004160  jbe     short loc_14000418B
0x140004162  lea     rax, [rbp+arg_0]
0x140004166  mov     [rbp+arg_0], 9Bh
0x14000416d  mov     [rsp+60h+var_38], rax
0x140004172  lea     rdx, byte_140010D37
0x140004179  lea     rax, [rbp+arg_10]
0x14000417d  mov     [rbp+arg_10], r14
0x140004181  mov     [rsp+60h+var_40], rax
0x140004186  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000418b  mov     eax, ebx
0x14000418d  add     rsp, 60h
0x140004191  pop     r14
0x140004193  pop     rdi
0x140004194  pop     rsi
0x140004195  pop     rbx
0x140004196  pop     rbp
0x140004197  retn
```
