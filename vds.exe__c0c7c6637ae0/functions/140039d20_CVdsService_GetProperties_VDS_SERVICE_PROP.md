# CVdsService::GetProperties(_VDS_SERVICE_PROP *)

- ea: `0x140039d20`
- end: `0x140039de5`
- name: `?GetProperties@CVdsService@@UEAAJPEAU_VDS_SERVICE_PROP@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct _VDS_SERVICE_PROP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140039d20`
- `0x14003ce10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039d56`
- `vdsutil!IsNoAutoMount` at `0x140039db3`
- `vdsutil!IsNoAutoMount` at `0x140039db3`
- `vdsutil!IsEfiFirmware` at `0x140039dc1`
- `vdsutil!IsEfiFirmware` at `0x140039dc1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039d3a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039d3a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140039dd7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140039dd7`
- `CLUSAPI!GetNodeClusterState` at `0x140039d9e`
- `CLUSAPI!GetNodeClusterState` at `0x140039d9e`

## string_xrefs

- `0x140039d29`: `CVdsService::GetProperties()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::GetProperties(CVdsService *this, struct _VDS_SERVICE_PROP *a2)
{
  wchar_t *v3; // rax
  size_t *v4; // r8
  unsigned int v5; // ebx
  WCHAR *v6; // r11
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF
  DWORD pdwClusterState; // [rsp+58h] [rbp+10h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v8, 0x5Eu, "CVdsService::GetProperties()");
  a2->pwszVersion = 0;
  a2->ulFlags = CVdsService::m_ulFlags;
  v3 = (wchar_t *)CoTaskMemAlloc(8u);
  if ( v3 )
  {
    StringCopyWorkerW(v3, 4u, v4, L"4.0", 0x7FFFFFFEu);
    a2->pwszVersion = v6;
    a2->ulFlags |= 4u;
    pdwClusterState = 0;
    if ( !GetNodeClusterState(0, &pdwClusterState) && (pdwClusterState & 2) != 0 )
      a2->ulFlags |= 0x10u;
    if ( (unsigned int)IsNoAutoMount() )
      a2->ulFlags |= 0x20u;
    if ( (unsigned int)IsEfiFirmware() )
      a2->ulFlags |= 0x80u;
    v5 = 0;
  }
  else
  {
    v5 = -2147024882;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v8);
  return v5;
}

```

## disassembly

```asm
0x140039d20  push    rbx
0x140039d22  sub     rsp, 40h
0x140039d26  mov     rbx, rdx
0x140039d29  lea     r8, aCvdsserviceGet_112; "CVdsService::GetProperties()"
0x140039d30  mov     edx, 5Eh ; '^'
0x140039d35  lea     rcx, [rsp+48h+var_18]
0x140039d3a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140039d40  nop
0x140039d41  mov     qword ptr [rbx], 0
0x140039d48  mov     eax, cs:?m_ulFlags@CVdsService@@0KA; ulong CVdsService::m_ulFlags
0x140039d4e  mov     [rbx+8], eax
0x140039d51  mov     ecx, 8; cb
0x140039d56  call    cs:__imp_CoTaskMemAlloc
0x140039d5c  mov     r11, rax
0x140039d5f  test    rax, rax
0x140039d62  jnz     short loc_140039D6B
0x140039d64  mov     ebx, 8007000Eh
0x140039d69  jmp     short loc_140039DD2
0x140039d6b  mov     [rsp+48h+cchToCopy], 7FFFFFFEh; cchToCopy
0x140039d74  lea     r9, a40; "4.0"
0x140039d7b  mov     edx, 4; cchDest
0x140039d80  mov     rcx, r11; pszDest
0x140039d83  call    StringCopyWorkerW
0x140039d88  mov     [rbx], r11
0x140039d8b  or      dword ptr [rbx+8], 4
0x140039d8f  mov     [rsp+48h+pdwClusterState], 0
0x140039d97  lea     rdx, [rsp+48h+pdwClusterState]; pdwClusterState
0x140039d9c  xor     ecx, ecx; lpszNodeName
0x140039d9e  call    cs:__imp_GetNodeClusterState
0x140039da4  test    eax, eax
0x140039da6  jnz     short loc_140039DB3
0x140039da8  test    byte ptr [rsp+48h+pdwClusterState], 2
0x140039dad  jz      short loc_140039DB3
0x140039daf  or      dword ptr [rbx+8], 10h
0x140039db3  call    cs:__imp_IsNoAutoMount
0x140039db9  test    eax, eax
0x140039dbb  jz      short loc_140039DC1
0x140039dbd  or      dword ptr [rbx+8], 20h
0x140039dc1  call    cs:__imp_IsEfiFirmware
0x140039dc7  test    eax, eax
0x140039dc9  jz      short loc_140039DD0
0x140039dcb  bts     dword ptr [rbx+8], 7
0x140039dd0  xor     ebx, ebx
0x140039dd2  lea     rcx, [rsp+48h+var_18]
0x140039dd7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140039ddd  mov     eax, ebx
0x140039ddf  add     rsp, 40h
0x140039de3  pop     rbx
0x140039de4  retn
```
