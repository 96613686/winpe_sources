# CVdsRawDiskLun::Offline(void)

- ea: `0x140026a10`
- end: `0x140026c05`
- name: `?Offline@CVdsRawDiskLun@@UEAAJXZ`
- size: `501`
- prototype: `__int64 __fastcall(CVdsRawDiskLun *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140026a10`
- `0x140029050`
- `0x14002e123`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026b4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026b65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026b7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026b4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026b65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026b7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026baa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026bc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026bc7`
- `vdsutil!OpenDevice` at `0x140026ad7`
- `vdsutil!OpenDevice` at `0x140026ad7`
- `vdsutil!VdsTraceExW` at `0x140026b3f`
- `vdsutil!VdsTraceExW` at `0x140026b3f`
- `vdsutil!VdsTraceEx` at `0x140026ac1`
- `vdsutil!VdsTraceEx` at `0x140026ac1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140026a5c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140026a5c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140026be5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140026be5`

## pseudocode

```c
__int64 __fastcall CVdsRawDiskLun::Offline(CVdsRawDiskLun *this)
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
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsRawDiskLun::Offline()");
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
      v5 = L"CVdsRawDiskLun::Offline, 2 Name=%s, Number=%ld, hr=%lX";
    }
    else
    {
      v2 = CVdsRawDiskLun::Offline((CVdsRawDiskLun *)((char *)this - 24), hObject);
      if ( v2 >= 0 )
        goto LABEL_13;
      v5 = L"CVdsRawDiskLun::Offline, 3 Name=%s, Number=%ld, hr=%lX";
    }
    v6 = L"UNKNOWN";
    if ( v17 )
      v6 = (const wchar_t *)v17;
    VdsTraceExW(94, 0, v5, v6, *((_DWORD *)this + 74), v2);
    goto LABEL_13;
  }
  VdsTraceEx(94, 0, "CVdsRawDiskLun::Offline, 1, hr=%lX", v3);
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
0x140026a10  push    rbp
0x140026a12  push    rbx
0x140026a13  push    rsi
0x140026a14  push    rdi
0x140026a15  lea     rbp, [rsp-3Fh]
0x140026a1a  sub     rsp, 0F8h
0x140026a21  mov     rax, cs:__security_cookie
0x140026a28  xor     rax, rsp
0x140026a2b  mov     [rbp+57h+var_30], rax
0x140026a2f  mov     rsi, rcx
0x140026a32  mov     [rsp+110h+hObject], 0
0x140026a3b  mov     edi, 80h
0x140026a40  mov     r8d, edi; Size
0x140026a43  xor     edx, edx; Val
0x140026a45  lea     rcx, [rbp+57h+var_B0]; void *
0x140026a49  call    memset_0
0x140026a4e  lea     r8, aCvdsrawdisklun_63; "CVdsRawDiskLun::Offline()"
0x140026a55  lea     edx, [rdi-22h]
0x140026a58  lea     rcx, [rbp+57h+var_C8]
0x140026a5c  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140026a62  nop
0x140026a63  mov     [rsp+110h+var_D8], 0
0x140026a6c  mov     [rbp+57h+var_D0], 0
0x140026a73  lea     rcx, [rsp+110h+var_D8]; this
0x140026a78  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140026a7d  mov     ebx, eax
0x140026a7f  test    eax, eax
0x140026a81  js      loc_140026BD6
0x140026a87  mov     r8d, edi; Size
0x140026a8a  xor     edx, edx; Val
0x140026a8c  lea     rcx, [rbp+57h+var_B0]; void *
0x140026a90  call    memset_0
0x140026a95  lea     rdi, [rsi-18h]
0x140026a99  mov     rax, [rdi]
0x140026a9c  lea     rdx, [rbp+57h+var_B0]
0x140026aa0  mov     rcx, rdi
0x140026aa3  mov     rax, [rax+18h]
0x140026aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026aac  mov     ebx, eax
0x140026aae  test    eax, eax
0x140026ab0  jns     short loc_140026AC9
0x140026ab2  mov     r9d, eax
0x140026ab5  lea     r8, aCvdsrawdisklun_66; "CVdsRawDiskLun::Offline, 1, hr=%lX"
0x140026abc  xor     edx, edx
0x140026abe  lea     ecx, [rdx+5Eh]
0x140026ac1  call    cs:__imp_VdsTraceEx
0x140026ac7  jmp     short loc_140026B45
0x140026ac9  lea     r8, [rsp+110h+hObject]
0x140026ace  mov     edx, 0C0000000h
0x140026ad3  mov     rcx, [rbp+57h+var_38]
0x140026ad7  call    cs:__imp_OpenDevice
0x140026add  mov     ebx, eax
0x140026adf  test    eax, eax
0x140026ae1  jz      short loc_140026B00
0x140026ae3  jle     short loc_140026AEE
0x140026ae5  movzx   ebx, ax
0x140026ae8  or      ebx, 80070000h
0x140026aee  mov     [rsp+110h+hObject], 0
0x140026af7  lea     r8, aCvdsrawdisklun_83; "CVdsRawDiskLun::Offline, 2 Name=%s, Num"...
0x140026afe  jmp     short loc_140026B1A
0x140026b00  mov     rdx, [rsp+110h+hObject]; void *
0x140026b05  mov     rcx, rdi; this
0x140026b08  call    ?Offline@CVdsRawDiskLun@@QEAAJPEAX@Z; CVdsRawDiskLun::Offline(void *)
0x140026b0d  mov     ebx, eax
0x140026b0f  test    eax, eax
0x140026b11  jns     short loc_140026B45
0x140026b13  lea     r8, aCvdsrawdisklun_37; "CVdsRawDiskLun::Offline, 3 Name=%s, Num"...
0x140026b1a  mov     rax, [rbp+57h+var_38]
0x140026b1e  lea     r9, aUnknown_0; "UNKNOWN"
0x140026b25  test    rax, rax
0x140026b28  mov     [rsp+110h+var_E8], ebx
0x140026b2c  mov     ecx, [rsi+128h]
0x140026b32  cmovnz  r9, rax
0x140026b36  mov     [rsp+110h+var_F0], ecx
0x140026b3a  xor     edx, edx
0x140026b3c  lea     ecx, [rdx+5Eh]
0x140026b3f  call    cs:__imp_VdsTraceExW
0x140026b45  mov     rcx, [rbp+57h+pv]; pv
0x140026b49  test    rcx, rcx
0x140026b4c  jz      short loc_140026B5C
0x140026b4e  call    cs:__imp_CoTaskMemFree
0x140026b54  mov     [rbp+57h+pv], 0
0x140026b5c  mov     rcx, [rbp+57h+var_48]; pv
0x140026b60  test    rcx, rcx
0x140026b63  jz      short loc_140026B73
0x140026b65  call    cs:__imp_CoTaskMemFree
0x140026b6b  mov     [rbp+57h+var_48], 0
0x140026b73  mov     rcx, [rbp+57h+var_38]; pv
0x140026b77  test    rcx, rcx
0x140026b7a  jz      short loc_140026B8A
0x140026b7c  call    cs:__imp_CoTaskMemFree
0x140026b82  mov     [rbp+57h+var_38], 0
0x140026b8a  mov     rcx, [rbp+57h+var_58]; pv
0x140026b8e  test    rcx, rcx
0x140026b91  jz      short loc_140026BA1
0x140026b93  call    cs:__imp_CoTaskMemFree
0x140026b99  mov     [rbp+57h+var_58], 0
0x140026ba1  mov     rcx, [rbp+57h+var_40]; pv
0x140026ba5  test    rcx, rcx
0x140026ba8  jz      short loc_140026BB8
0x140026baa  call    cs:__imp_CoTaskMemFree
0x140026bb0  mov     [rbp+57h+var_40], 0
0x140026bb8  mov     rcx, [rsp+110h+hObject]; hObject
0x140026bbd  lea     rax, [rcx-1]
0x140026bc1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140026bc5  ja      short loc_140026BD6
0x140026bc7  call    cs:__imp_CloseHandle
0x140026bcd  mov     [rsp+110h+hObject], 0FFFFFFFFFFFFFFFFh
0x140026bd6  lea     rcx, [rsp+110h+var_D8]; this
0x140026bdb  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140026be0  nop
0x140026be1  lea     rcx, [rbp+57h+var_C8]
0x140026be5  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140026beb  mov     eax, ebx
0x140026bed  mov     rcx, [rbp+57h+var_30]
0x140026bf1  xor     rcx, rsp; StackCookie
0x140026bf4  call    __security_check_cookie
0x140026bf9  add     rsp, 0F8h
0x140026c00  pop     rdi
0x140026c01  pop     rsi
0x140026c02  pop     rbx
0x140026c03  pop     rbp
0x140026c04  retn
```
