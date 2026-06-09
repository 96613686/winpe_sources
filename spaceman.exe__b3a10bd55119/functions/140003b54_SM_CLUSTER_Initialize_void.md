# SM_CLUSTER::Initialize(void)

- ea: `0x140003b54`
- end: `0x140003c77`
- name: `?Initialize@SM_CLUSTER@@QEAAHXZ`
- size: `291`
- prototype: `__int64 __fastcall(SM_CLUSTER *this, __int64, int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140002c1c`
- `0x140002f20`
- `0x1400032b0`
- `0x140003494`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x140003b54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003be4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003bec`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x140003b9f`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x140003b9f`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterKey` at `0x140003bb5`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterKey` at `0x140003bb5`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegOpenKey` at `0x140003bd8`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegOpenKey` at `0x140003bd8`

## pseudocode

```c
__int64 __fastcall SM_CLUSTER::Initialize(SM_CLUSTER *this, __int64 a2, int a3, int a4)
{
  struct _HCLUSTER *v5; // rax
  HKEY ClusterKey; // rax
  LONG v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  unsigned int v11; // ebx
  DWORD LastError; // eax
  int v13; // r8d
  int v14; // r9d
  int v16; // [rsp+60h] [rbp+20h] BYREF
  const char *v17; // [rsp+68h] [rbp+28h] BYREF
  const char *v18; // [rsp+70h] [rbp+30h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v16 = 71;
    v17 = "SM_CLUSTER::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)qword_140010B90,
      a3,
      a4,
      (__int64)&v17,
      (__int64)&v16);
  }
  v5 = OpenCluster(0);
  *(_QWORD *)this = v5;
  if ( !v5 )
    goto LABEL_7;
  ClusterKey = GetClusterKey(v5, 2u);
  *((_QWORD *)this + 1) = ClusterKey;
  if ( !ClusterKey )
    goto LABEL_7;
  v7 = ClusterRegOpenKey(ClusterKey, L"Spaceport\\Witness", 0x2001Fu, (PHKEY)this + 2);
  if ( v7 )
  {
    SetLastError(v7);
LABEL_7:
    v11 = 0;
    LastError = GetLastError();
    if ( (unsigned int)dword_140014048 > 2 )
    {
      v16 = LastError;
      LODWORD(v17) = 104;
      v18 = "SM_CLUSTER::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_140014048,
        (unsigned int)qword_140010F10,
        v13,
        v14,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16);
    }
    return v11;
  }
  v11 = 1;
  if ( (unsigned int)dword_140014048 > 5 )
  {
    v16 = 104;
    v17 = "SM_CLUSTER::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)byte_140010EE3,
      v9,
      v10,
      (__int64)&v17,
      (__int64)&v16);
  }
  return v11;
}

```

## disassembly

```asm
0x140003b54  push    rbp
0x140003b56  push    rbx
0x140003b57  push    rdi
0x140003b58  mov     rbp, rsp
0x140003b5b  sub     rsp, 40h
0x140003b5f  mov     eax, cs:dword_140014048
0x140003b65  lea     rdi, aSmClusterIniti; "SM_CLUSTER::Initialize"
0x140003b6c  mov     rbx, rcx
0x140003b6f  cmp     eax, 5
0x140003b72  jbe     short loc_140003B9D
0x140003b74  lea     rax, [rbp+arg_0]
0x140003b78  mov     [rbp+arg_0], 47h ; 'G'
0x140003b7f  mov     [rsp+40h+var_18], rax
0x140003b84  lea     rdx, qword_140010B90
0x140003b8b  lea     rax, [rbp+arg_8]
0x140003b8f  mov     [rbp+arg_8], rdi
0x140003b93  mov     [rsp+40h+var_20], rax
0x140003b98  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003b9d  xor     ecx, ecx; lpszClusterName
0x140003b9f  call    cs:__imp_OpenCluster
0x140003ba5  mov     [rbx], rax
0x140003ba8  test    rax, rax
0x140003bab  jz      short loc_140003BEA
0x140003bad  mov     edx, 2; samDesired
0x140003bb2  mov     rcx, rax; hCluster
0x140003bb5  call    cs:__imp_GetClusterKey
0x140003bbb  mov     [rbx+8], rax
0x140003bbf  test    rax, rax
0x140003bc2  jz      short loc_140003BEA
0x140003bc4  lea     r9, [rbx+10h]; phkResult
0x140003bc8  mov     r8d, 2001Fh; samDesired
0x140003bce  lea     rdx, szSubKey; "Spaceport\\Witness"
0x140003bd5  mov     rcx, rax; hKey
0x140003bd8  call    cs:__imp_ClusterRegOpenKey
0x140003bde  test    eax, eax
0x140003be0  jz      short loc_140003C3C
0x140003be2  mov     ecx, eax; dwErrCode
0x140003be4  call    cs:__imp_SetLastError
0x140003bea  xor     ebx, ebx
0x140003bec  call    cs:__imp_GetLastError
0x140003bf2  mov     ecx, cs:dword_140014048
0x140003bf8  cmp     ecx, 2
0x140003bfb  jbe     short loc_140003C32
0x140003bfd  mov     [rbp+arg_0], eax
0x140003c00  lea     rdx, qword_140010F10
0x140003c07  lea     rax, [rbp+arg_0]
0x140003c0b  mov     dword ptr [rbp+arg_8], 68h ; 'h'
0x140003c12  mov     [rsp+40h+var_10], rax
0x140003c17  lea     rax, [rbp+arg_8]
0x140003c1b  mov     [rsp+40h+var_18], rax
0x140003c20  lea     rax, [rbp+arg_10]
0x140003c24  mov     [rsp+40h+var_20], rax
0x140003c29  mov     [rbp+arg_10], rdi
0x140003c2d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003c32  mov     eax, ebx
0x140003c34  add     rsp, 40h
0x140003c38  pop     rdi
0x140003c39  pop     rbx
0x140003c3a  pop     rbp
0x140003c3b  retn
0x140003c3c  mov     ebx, 1
0x140003c41  mov     eax, cs:dword_140014048
0x140003c47  cmp     eax, 5
0x140003c4a  jbe     short loc_140003C32
0x140003c4c  lea     rax, [rbp+arg_0]
0x140003c50  mov     [rbp+arg_0], 68h ; 'h'
0x140003c57  mov     [rsp+40h+var_18], rax
0x140003c5c  lea     rdx, byte_140010EE3
0x140003c63  lea     rax, [rbp+arg_8]
0x140003c67  mov     [rbp+arg_8], rdi
0x140003c6b  mov     [rsp+40h+var_20], rax
0x140003c70  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003c75  jmp     short loc_140003C32
```
