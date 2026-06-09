# CVdsService::AddNetworkShare(ushort *)

- ea: `0x140037674`
- end: `0x140037739`
- name: `?AddNetworkShare@CVdsService@@SAHPEAG@Z`
- size: `197`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140022e80`

## callees

- `0x140037674`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140037698`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140037698`
- `vdsutil!VdsTraceEx` at `0x1400376b4`
- `vdsutil!VdsTraceEx` at `0x140037721`
- `vdsutil!VdsTraceEx` at `0x14003772e`
- `vdsutil!VdsTraceEx` at `0x1400376b4`
- `vdsutil!VdsTraceEx` at `0x140037721`
- `vdsutil!VdsTraceEx` at `0x14003772e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003768e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003768e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400376c4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400376c4`
- `srvcli!NetShareAdd` at `0x1400376fd`
- `srvcli!NetShareAdd` at `0x1400376fd`

## string_xrefs

- `0x14003767d`: `CVdsService::AddNetworkShare()`
- `0x1400376aa`: `CVdsService::AddNetworkShare: Skipping NetShareAdd(): GetDriveType() == %u`
- `0x14003770d`: `CVdsService::AddNetworkShare: NetShareAdd() failed: %ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::AddNetworkShare(LPCWSTR lpRootPathName)
{
  UINT DriveTypeW; // eax
  unsigned int v3; // ebx
  DWORD v5; // eax
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v6, 0x5Eu, "CVdsService::AddNetworkShare()");
  DriveTypeW = GetDriveTypeW(lpRootPathName);
  if ( DriveTypeW != 3 )
  {
    VdsTraceEx(94, 3, "CVdsService::AddNetworkShare: Skipping NetShareAdd(): GetDriveType() == %u", DriveTypeW);
LABEL_3:
    v3 = 1;
    goto LABEL_4;
  }
  **(_WORD **)&CVdsService::m_ShareInfo502 = *lpRootPathName;
  *(_WORD *)qword_14009B058 = *lpRootPathName;
  v5 = NetShareAdd(0, 0x1F6u, &CVdsService::m_ShareInfo502, 0);
  if ( !v5 )
    goto LABEL_3;
  if ( v5 == 2118 )
    VdsTraceEx(94, 1, "CVdsService::AddNetworkShare: NetShareAdd() failed: %ld", 2118);
  else
    VdsTraceEx(94, 0, "CVdsService::AddNetworkShare: NetShareAdd() failed: %ld", v5);
  v3 = 0;
LABEL_4:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v6);
  return v3;
}

```

## disassembly

```asm
0x140037674  push    rbx
0x140037676  sub     rsp, 30h
0x14003767a  mov     rbx, rcx
0x14003767d  lea     r8, aCvdsserviceAdd_4; "CVdsService::AddNetworkShare()"
0x140037684  mov     edx, 5Eh ; '^'
0x140037689  lea     rcx, [rsp+38h+var_18]
0x14003768e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140037694  nop
0x140037695  mov     rcx, rbx; lpRootPathName
0x140037698  call    cs:__imp_GetDriveTypeW
0x14003769e  mov     edx, 3
0x1400376a3  cmp     eax, edx
0x1400376a5  jz      short loc_1400376D2
0x1400376a7  mov     r9d, eax
0x1400376aa  lea     r8, aCvdsserviceAdd_15; "CVdsService::AddNetworkShare: Skipping "...
0x1400376b1  lea     ecx, [rdx+5Bh]
0x1400376b4  call    cs:__imp_VdsTraceEx
0x1400376ba  mov     ebx, 1
0x1400376bf  lea     rcx, [rsp+38h+var_18]
0x1400376c4  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400376ca  mov     eax, ebx
0x1400376cc  add     rsp, 30h
0x1400376d0  pop     rbx
0x1400376d1  retn
0x1400376d2  movzx   ecx, word ptr [rbx]
0x1400376d5  mov     rax, cs:?m_ShareInfo502@CVdsService@@0U_SHARE_INFO_502@@A; _SHARE_INFO_502 CVdsService::m_ShareInfo502
0x1400376dc  mov     [rax], cx
0x1400376df  movzx   ecx, word ptr [rbx]
0x1400376e2  mov     rax, cs:qword_14009B058
0x1400376e9  mov     [rax], cx
0x1400376ec  xor     r9d, r9d; parm_err
0x1400376ef  lea     r8, ?m_ShareInfo502@CVdsService@@0U_SHARE_INFO_502@@A; buf
0x1400376f6  mov     edx, 1F6h; level
0x1400376fb  xor     ecx, ecx; servername
0x1400376fd  call    cs:__imp_NetShareAdd
0x140037703  test    eax, eax
0x140037705  jz      short loc_1400376BA
0x140037707  mov     r9d, 846h
0x14003770d  lea     r8, aCvdsserviceAdd_13; "CVdsService::AddNetworkShare: NetShareA"...
0x140037714  mov     ecx, 5Eh ; '^'
0x140037719  cmp     eax, r9d
0x14003771c  jnz     short loc_140037729
0x14003771e  lea     edx, [rcx-5Dh]
0x140037721  call    cs:__imp_VdsTraceEx
0x140037727  jmp     short loc_140037734
0x140037729  mov     r9d, eax
0x14003772c  xor     edx, edx
0x14003772e  call    cs:__imp_VdsTraceEx
0x140037734  xor     ebx, ebx
0x140037736  jmp     short loc_1400376BF
```
