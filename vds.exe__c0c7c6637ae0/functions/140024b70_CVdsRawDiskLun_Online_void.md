# CVdsRawDiskLun::Online(void)

- ea: `0x140024b70`
- end: `0x140024d65`
- name: `?Online@CVdsRawDiskLun@@UEAAJXZ`
- size: `501`
- prototype: `__int64 __fastcall(CVdsRawDiskLun *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140024b70`
- `0x140027cd8`
- `0x14002e123`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024cae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024cc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024d0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024cae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024cc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024d0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024d27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024d27`
- `vdsutil!OpenDevice` at `0x140024c37`
- `vdsutil!OpenDevice` at `0x140024c37`
- `vdsutil!VdsTraceExW` at `0x140024c9f`
- `vdsutil!VdsTraceExW` at `0x140024c9f`
- `vdsutil!VdsTraceEx` at `0x140024c21`
- `vdsutil!VdsTraceEx` at `0x140024c21`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140024bbc`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140024bbc`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140024d45`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140024d45`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsRawDiskLun::Online(CVdsRawDiskLun *this)
{
  int v2; // ebx
  int v3; // eax
  int v4; // eax
  const wchar_t *v5; // r8
  const wchar_t *v6; // r9
  HANDLE hObject; // [rsp+30h] [rbp-89h] BYREF
  __int64 v9; // [rsp+38h] [rbp-81h] BYREF
  int v10; // [rsp+40h] [rbp-79h]
  _BYTE v11[24]; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v12[88]; // [rsp+60h] [rbp-59h] BYREF
  LPVOID v13; // [rsp+B8h] [rbp-1h]
  LPVOID pv; // [rsp+C0h] [rbp+7h]
  LPVOID v15; // [rsp+C8h] [rbp+Fh]
  LPVOID v16; // [rsp+D0h] [rbp+17h]
  LPVOID v17; // [rsp+D8h] [rbp+1Fh]

  hObject = 0;
  memset_0(v12, 0, 0x80u);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsRawDiskLun::Online()");
  v9 = 0;
  v10 = 0;
  v2 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v9);
  if ( v2 < 0 )
    goto LABEL_25;
  memset_0(v12, 0, 0x80u);
  v3 = (*(__int64 (__fastcall **)(char *, _BYTE *))(*((_QWORD *)this - 3) + 24LL))((char *)this - 24, v12);
  v2 = v3;
  if ( v3 >= 0 )
  {
    v4 = OpenDevice(v17, 3221225472LL, &hObject);
    v2 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      hObject = 0;
      v5 = L"CVdsRawDiskLun::Online, 2 Name=%s, Number=%ld, hr=%lX";
    }
    else
    {
      v2 = CVdsRawDiskLun::Online((CVdsRawDiskLun *)((char *)this - 24), hObject);
      if ( v2 >= 0 )
        goto LABEL_13;
      v5 = L"CVdsRawDiskLun::Online, 3 Name=%s, Number=%ld, hr=%lX";
    }
    v6 = L"UNKNOWN";
    if ( v17 )
      v6 = (const wchar_t *)v17;
    VdsTraceExW(94, 0, v5, v6, *((_DWORD *)this + 74), v2);
    goto LABEL_13;
  }
  VdsTraceEx(94, 0, "CVdsRawDiskLun::Online, 1, hr=%lX", v3);
LABEL_13:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v15 = 0;
  }
  if ( v17 )
  {
    CoTaskMemFree(v17);
    v17 = 0;
  }
  if ( v13 )
  {
    CoTaskMemFree(v13);
    v13 = 0;
  }
  if ( v16 )
  {
    CoTaskMemFree(v16);
    v16 = 0;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
LABEL_25:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v9);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140024b70  push    rbp
0x140024b72  push    rbx
0x140024b73  push    rsi
0x140024b74  push    rdi
0x140024b75  lea     rbp, [rsp-3Fh]
0x140024b7a  sub     rsp, 0F8h
0x140024b81  mov     rax, cs:__security_cookie
0x140024b88  xor     rax, rsp
0x140024b8b  mov     [rbp+57h+var_30], rax
0x140024b8f  mov     rsi, rcx
0x140024b92  mov     [rsp+110h+hObject], 0
0x140024b9b  mov     edi, 80h
0x140024ba0  mov     r8d, edi; Size
0x140024ba3  xor     edx, edx; Val
0x140024ba5  lea     rcx, [rbp+57h+var_B0]; void *
0x140024ba9  call    memset_0
0x140024bae  lea     r8, aCvdsrawdisklun; "CVdsRawDiskLun::Online()"
0x140024bb5  lea     edx, [rdi-22h]
0x140024bb8  lea     rcx, [rbp+57h+var_C8]
0x140024bbc  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140024bc2  nop
0x140024bc3  mov     [rsp+110h+var_D8], 0
0x140024bcc  mov     [rbp+57h+var_D0], 0
0x140024bd3  lea     rcx, [rsp+110h+var_D8]; this
0x140024bd8  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140024bdd  mov     ebx, eax
0x140024bdf  test    eax, eax
0x140024be1  js      loc_140024D36
0x140024be7  mov     r8d, edi; Size
0x140024bea  xor     edx, edx; Val
0x140024bec  lea     rcx, [rbp+57h+var_B0]; void *
0x140024bf0  call    memset_0
0x140024bf5  lea     rdi, [rsi-18h]
0x140024bf9  mov     rax, [rdi]
0x140024bfc  lea     rdx, [rbp+57h+var_B0]
0x140024c00  mov     rcx, rdi
0x140024c03  mov     rax, [rax+18h]
0x140024c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c0c  mov     ebx, eax
0x140024c0e  test    eax, eax
0x140024c10  jns     short loc_140024C29
0x140024c12  mov     r9d, eax
0x140024c15  lea     r8, aCvdsrawdisklun_67; "CVdsRawDiskLun::Online, 1, hr=%lX"
0x140024c1c  xor     edx, edx
0x140024c1e  lea     ecx, [rdx+5Eh]
0x140024c21  call    cs:__imp_VdsTraceEx
0x140024c27  jmp     short loc_140024CA5
0x140024c29  lea     r8, [rsp+110h+hObject]
0x140024c2e  mov     edx, 0C0000000h
0x140024c33  mov     rcx, [rbp+57h+var_38]
0x140024c37  call    cs:__imp_OpenDevice
0x140024c3d  mov     ebx, eax
0x140024c3f  test    eax, eax
0x140024c41  jz      short loc_140024C60
0x140024c43  jle     short loc_140024C4E
0x140024c45  movzx   ebx, ax
0x140024c48  or      ebx, 80070000h
0x140024c4e  mov     [rsp+110h+hObject], 0
0x140024c57  lea     r8, aCvdsrawdisklun_91; "CVdsRawDiskLun::Online, 2 Name=%s, Numb"...
0x140024c5e  jmp     short loc_140024C7A
0x140024c60  mov     rdx, [rsp+110h+hObject]; void *
0x140024c65  mov     rcx, rdi; this
0x140024c68  call    ?Online@CVdsRawDiskLun@@QEAAJPEAX@Z; CVdsRawDiskLun::Online(void *)
0x140024c6d  mov     ebx, eax
0x140024c6f  test    eax, eax
0x140024c71  jns     short loc_140024CA5
0x140024c73  lea     r8, aCvdsrawdisklun_39; "CVdsRawDiskLun::Online, 3 Name=%s, Numb"...
0x140024c7a  mov     rax, [rbp+57h+var_38]
0x140024c7e  lea     r9, aUnknown_0; "UNKNOWN"
0x140024c85  test    rax, rax
0x140024c88  mov     [rsp+110h+var_E8], ebx
0x140024c8c  mov     ecx, [rsi+128h]
0x140024c92  cmovnz  r9, rax
0x140024c96  mov     [rsp+110h+var_F0], ecx
0x140024c9a  xor     edx, edx
0x140024c9c  lea     ecx, [rdx+5Eh]
0x140024c9f  call    cs:__imp_VdsTraceExW
0x140024ca5  mov     rcx, [rbp+57h+pv]; pv
0x140024ca9  test    rcx, rcx
0x140024cac  jz      short loc_140024CBC
0x140024cae  call    cs:__imp_CoTaskMemFree
0x140024cb4  mov     [rbp+57h+pv], 0
0x140024cbc  mov     rcx, [rbp+57h+var_48]; pv
0x140024cc0  test    rcx, rcx
0x140024cc3  jz      short loc_140024CD3
0x140024cc5  call    cs:__imp_CoTaskMemFree
0x140024ccb  mov     [rbp+57h+var_48], 0
0x140024cd3  mov     rcx, [rbp+57h+var_38]; pv
0x140024cd7  test    rcx, rcx
0x140024cda  jz      short loc_140024CEA
0x140024cdc  call    cs:__imp_CoTaskMemFree
0x140024ce2  mov     [rbp+57h+var_38], 0
0x140024cea  mov     rcx, [rbp+57h+var_58]; pv
0x140024cee  test    rcx, rcx
0x140024cf1  jz      short loc_140024D01
0x140024cf3  call    cs:__imp_CoTaskMemFree
0x140024cf9  mov     [rbp+57h+var_58], 0
0x140024d01  mov     rcx, [rbp+57h+var_40]; pv
0x140024d05  test    rcx, rcx
0x140024d08  jz      short loc_140024D18
0x140024d0a  call    cs:__imp_CoTaskMemFree
0x140024d10  mov     [rbp+57h+var_40], 0
0x140024d18  mov     rcx, [rsp+110h+hObject]; hObject
0x140024d1d  lea     rax, [rcx-1]
0x140024d21  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140024d25  ja      short loc_140024D36
0x140024d27  call    cs:__imp_CloseHandle
0x140024d2d  mov     [rsp+110h+hObject], 0FFFFFFFFFFFFFFFFh
0x140024d36  lea     rcx, [rsp+110h+var_D8]; this
0x140024d3b  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140024d40  nop
0x140024d41  lea     rcx, [rbp+57h+var_C8]
0x140024d45  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140024d4b  mov     eax, ebx
0x140024d4d  mov     rcx, [rbp+57h+var_30]
0x140024d51  xor     rcx, rsp; StackCookie
0x140024d54  call    __security_check_cookie
0x140024d59  add     rsp, 0F8h
0x140024d60  pop     rdi
0x140024d61  pop     rsi
0x140024d62  pop     rbx
0x140024d63  pop     rbp
0x140024d64  retn
```
