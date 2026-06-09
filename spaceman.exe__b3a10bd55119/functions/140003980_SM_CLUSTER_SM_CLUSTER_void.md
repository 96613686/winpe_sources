# SM_CLUSTER::~SM_CLUSTER(void)

- ea: `0x140003980`
- end: `0x140003a38`
- name: `??1SM_CLUSTER@@QEAA@XZ`
- size: `184`
- prototype: `void __fastcall(SM_CLUSTER *this, __int64, __int64, __int64)`
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
- `0x140003980`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x1400039ef`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x1400039ef`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegCloseKey` at `0x1400039d2`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegCloseKey` at `0x1400039e1`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegCloseKey` at `0x1400039d2`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegCloseKey` at `0x1400039e1`

## pseudocode

```c
void __fastcall SM_CLUSTER::~SM_CLUSTER(SM_CLUSTER *this, __int64 a2, __int64 a3, __int64 a4)
{
  HKEY v5; // rcx
  HKEY v6; // rcx
  struct _HCLUSTER *v7; // rcx
  int v8; // [rsp+40h] [rbp+8h] BYREF
  const char *v9; // [rsp+48h] [rbp+10h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v8 = 49;
    v9 = "SM_CLUSTER::~SM_CLUSTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&dword_140010E54,
      a3,
      a4,
      (const unsigned __int16 **)&v9,
      (__int64)&v8);
  }
  v5 = (HKEY)*((_QWORD *)this + 2);
  if ( v5 )
    ClusterRegCloseKey(v5);
  v6 = (HKEY)*((_QWORD *)this + 1);
  if ( v6 )
    ClusterRegCloseKey(v6);
  v7 = *(struct _HCLUSTER **)this;
  if ( *(_QWORD *)this )
    CloseCluster(v7);
  if ( (unsigned int)dword_140014048 > 5 )
  {
    v8 = 63;
    v9 = "SM_CLUSTER::~SM_CLUSTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v7,
      (__int64)&dword_140010D64,
      a3,
      a4,
      (const unsigned __int16 **)&v9,
      (__int64)&v8);
  }
}

```

## disassembly

```asm
0x140003980  mov     r11, rsp
0x140003983  mov     [r11+18h], rbx
0x140003987  push    rdi
0x140003988  sub     rsp, 30h
0x14000398c  mov     eax, cs:dword_140014048
0x140003992  lea     rdi, aSmClusterSmClu_0; "SM_CLUSTER::~SM_CLUSTER"
0x140003999  mov     rbx, rcx
0x14000399c  cmp     eax, 5
0x14000399f  jbe     short loc_1400039C9
0x1400039a1  lea     rax, [r11+8]
0x1400039a5  mov     [rsp+38h+arg_0], 31h ; '1'
0x1400039ad  mov     [r11-10h], rax
0x1400039b1  lea     rdx, dword_140010E54
0x1400039b8  lea     rax, [r11+10h]
0x1400039bc  mov     [r11+10h], rdi
0x1400039c0  mov     [r11-18h], rax
0x1400039c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400039c9  mov     rcx, [rbx+10h]; hKey
0x1400039cd  test    rcx, rcx
0x1400039d0  jz      short loc_1400039D8
0x1400039d2  call    cs:__imp_ClusterRegCloseKey
0x1400039d8  mov     rcx, [rbx+8]; hKey
0x1400039dc  test    rcx, rcx
0x1400039df  jz      short loc_1400039E7
0x1400039e1  call    cs:__imp_ClusterRegCloseKey
0x1400039e7  mov     rcx, [rbx]; hCluster
0x1400039ea  test    rcx, rcx
0x1400039ed  jz      short loc_1400039F5
0x1400039ef  call    cs:__imp_CloseCluster
0x1400039f5  mov     eax, cs:dword_140014048
0x1400039fb  cmp     eax, 5
0x1400039fe  jbe     short loc_140003A2D
0x140003a00  lea     rax, [rsp+38h+arg_0]
0x140003a05  mov     [rsp+38h+arg_0], 3Fh ; '?'
0x140003a0d  mov     [rsp+38h+var_10], rax
0x140003a12  lea     rdx, dword_140010D64
0x140003a19  lea     rax, [rsp+38h+arg_8]
0x140003a1e  mov     [rsp+38h+arg_8], rdi
0x140003a23  mov     [rsp+38h+var_18], rax
0x140003a28  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003a2d  mov     rbx, [rsp+38h+arg_10]
0x140003a32  add     rsp, 30h
0x140003a36  pop     rdi
0x140003a37  retn
```
