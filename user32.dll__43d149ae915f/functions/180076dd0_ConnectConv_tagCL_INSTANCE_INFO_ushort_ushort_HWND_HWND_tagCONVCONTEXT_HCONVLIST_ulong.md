# ConnectConv(tagCL_INSTANCE_INFO *,ushort,ushort,HWND__ *,HWND__ *,tagCONVCONTEXT *,HCONVLIST__ *,ulong)

- ea: `0x180076dd0`
- end: `0x180077100`
- name: `?ConnectConv@@YAPEAUtagCL_CONV_INFO@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHWND__@@1PEAUtagCONVCONTEXT@@PEAUHCONVLIST__@@K@Z`
- size: `816`
- prototype: `struct tagCL_CONV_INFO *(struct tagCL_INSTANCE_INFO *, unsigned __int16, unsigned __int16, HWND, HWND, struct tagCONVCONTEXT *, HCONVLIST, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callers

- `0x180077260`
- `0x180077370`
- `0x180077740`

## callees

- `0x18000bd00`
- `0x18000e760`
- `0x180016310`
- `0x18002d6c0`
- `0x18002dd20`
- `0x1800301a0`
- `0x1800481f4`
- `0x18004825c`
- `0x18004dce4`
- `0x18004e41c`
- `0x180076dd0`
- `0x18008808c`

## import_xrefs

- `win32u!NtUserDestroyWindow` at `0x180077063`
- `win32u!NtUserDestroyWindow` at `0x180077063`
- `ntdll!RtlEnterCriticalSection` at `0x180076ea2`
- `ntdll!RtlEnterCriticalSection` at `0x180077025`
- `ntdll!RtlEnterCriticalSection` at `0x180077070`
- `ntdll!RtlEnterCriticalSection` at `0x180076ea2`
- `ntdll!RtlEnterCriticalSection` at `0x180077025`
- `ntdll!RtlEnterCriticalSection` at `0x180077070`
- `ntdll!RtlLeaveCriticalSection` at `0x180076e2b`
- `ntdll!RtlLeaveCriticalSection` at `0x180076f66`
- `ntdll!RtlLeaveCriticalSection` at `0x180077059`
- `ntdll!RtlLeaveCriticalSection` at `0x180076e2b`
- `ntdll!RtlLeaveCriticalSection` at `0x180076f66`
- `ntdll!RtlLeaveCriticalSection` at `0x180077059`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007702f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180077039`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007702f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180077039`

## string_xrefs

- `0x180076fa9`: `NetDDE Agent`

## pseudocode

```c
struct tagCL_CONV_INFO *__fastcall ConnectConv(
        struct tagCL_INSTANCE_INFO *a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        HWND a4,
        HWND a5,
        struct tagCONVCONTEXT *a6,
        HCONVLIST a7,
        unsigned int a8)
{
  unsigned int v8; // edi
  HWND v12; // rax
  UINT cb; // r8d
  int v16; // r13d
  HWND Window; // rax
  LONG_PTR WindowLongPtrW; // rdi
  LONG_PTR v19; // rbx
  HWND hWndParent; // [rsp+48h] [rbp-39h]
  unsigned __int64 v21; // [rsp+68h] [rbp-19h] BYREF
  HWND hWnd[2]; // [rsp+70h] [rbp-11h] BYREF
  __int128 v23; // [rsp+80h] [rbp-1h]
  __int64 v24; // [rsp+90h] [rbp+Fh]
  ATOM v26; // [rsp+E0h] [rbp+5Fh]

  v8 = 0;
  v24 = 0;
  v21 = 0;
  *(_OWORD *)hWnd = 0;
  v23 = 0;
  if ( a4 && a4 == a5 )
    return 0;
  RtlLeaveCriticalSection(&gcsDDEML);
  hWndParent = (HWND)*((_QWORD *)a1 + 4);
  v12 = *((__int16 *)a1 + 54) >= 0
      ? CreateWindowExA(
          0,
          (LPCSTR)*(unsigned __int16 *)(gpsi + 890),
          byte_1800AB024,
          0x40000000u,
          0,
          0,
          0,
          0,
          hWndParent,
          0,
          0,
          0)
      : CreateWindowExW(
          0,
          (LPCWSTR)*(unsigned __int16 *)(gpsi + 892),
          &pszFormat,
          0x40000000u,
          0,
          0,
          0,
          0,
          hWndParent,
          0,
          0,
          0);
  hWnd[0] = v12;
  RtlEnterCriticalSection(&gcsDDEML);
  if ( !hWnd[0] )
    return 0;
  do
  {
    cb = a6->cb;
    a6 = (struct tagCONVCONTEXT *)((char *)a6 + 4);
    _SetWindowLong(hWnd[0], v8 + 8, cb, 0);
    v8 += 4;
  }
  while ( v8 < 0x24 );
  _SetWindowLong(hWnd[0], 44, a8, 0);
  SetWindowLongPtrW(hWnd[0], 48, *((_QWORD *)a1 + 1));
  SetWindowLongPtrW(hWnd[0], 56, *((_QWORD *)a1 + 2));
  v16 = LocalToGlobalAtom(a2);
  v26 = LocalToGlobalAtom(a3);
  LODWORD(v23) = v16 | (v26 << 16);
  if ( !a4 )
  {
    hWnd[1] = a5;
    *((_QWORD *)&v23 + 1) = a7;
    WORD2(v23) = a2;
    WORD3(v23) = a3;
    LODWORD(v24) = a8;
  }
  RtlLeaveCriticalSection(&gcsDDEML);
  if ( a4 )
  {
    SendMessageTimeoutWorker(a4, 0x3E0u, (unsigned __int64)hWnd[0], (int)v23, 0x12u, 0x3A98u, &v21, 0);
  }
  else
  {
    Window = FindWindowExW(0, 0, L"NDDEAgnt", L"NetDDE Agent");
    if ( Window )
      SendMessageTimeoutWorker(Window, 0x3E0u, (unsigned __int64)hWnd[0], (int)v23, 0x12u, 0x3A98u, &v21, 0);
    EnumWindowsWorker(0, 0, (int (*)(HWND, __int64))InitiateEnumerationProc, (__int64)hWnd, 0, 0, 1);
  }
  RtlEnterCriticalSection(&gcsDDEML);
  GlobalDeleteAtom(v16);
  GlobalDeleteAtom(v26);
  WindowLongPtrW = GetWindowLongPtrW(hWnd[0], 0);
  if ( !WindowLongPtrW )
  {
    RtlLeaveCriticalSection(&gcsDDEML);
    NtUserDestroyWindow(hWnd[0]);
    RtlEnterCriticalSection(&gcsDDEML);
    return 0;
  }
  _SetWindowLong(hWnd[0], 44, 0, 0);
  if ( a4 )
  {
    *(_QWORD *)(WindowLongPtrW + 112) = a4;
    *(_WORD *)(WindowLongPtrW + 58) = a2;
    IncLocalAtomCount(a2);
  }
  if ( (*((_DWORD *)a1 + 6) & 0x40000000) != 0 )
  {
    v19 = WindowLongPtrW;
    do
    {
      if ( (*(_DWORD *)(*(_QWORD *)(v19 + 8) + 24LL) & 0x40000000) != 0
        && ((*(_BYTE *)(v19 + 56) & 4) == 0 || (*(_BYTE *)(v19 + 56) & 0x10) != 0) )
      {
        MonitorConv((struct tagCONV_INFO *)v19, 1);
      }
      v19 = *(_QWORD *)v19;
    }
    while ( v19 );
  }
  return (struct tagCL_CONV_INFO *)WindowLongPtrW;
}

```

## disassembly

```asm
0x180076dd0  mov     rax, rsp
0x180076dd3  mov     [rax+8], rbx
0x180076dd7  mov     [rax+10h], rdi
0x180076ddb  mov     [rax+18h], r8w
0x180076de0  push    rbp
0x180076de1  push    r12
0x180076de3  push    r13
0x180076de5  push    r14
0x180076de7  push    r15
0x180076de9  lea     rbp, [rax-3Fh]
0x180076ded  sub     rsp, 90h
0x180076df4  xor     eax, eax
0x180076df6  xor     edi, edi
0x180076df8  mov     [rbp+37h+var_28], rax
0x180076dfc  xorps   xmm0, xmm0
0x180076dff  mov     [rbp+37h+var_50], rdi
0x180076e03  mov     rbx, r9
0x180076e06  movzx   r12d, dx
0x180076e0a  mov     r14, rcx
0x180076e0d  movups  xmmword ptr [rbp+37h+hWnd], xmm0
0x180076e11  movups  [rbp+37h+var_38], xmm0
0x180076e15  test    r9, r9
0x180076e18  jz      short loc_180076E24
0x180076e1a  cmp     rbx, [rbp+37h+arg_20]
0x180076e1e  jz      loc_180076EB1
0x180076e24  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180076e2b  call    cs:__imp_RtlLeaveCriticalSection
0x180076e31  mov     rcx, [r14+20h]
0x180076e35  mov     r9d, 40000000h; dwStyle
0x180076e3b  mov     rax, cs:gpsi
0x180076e42  mov     [rsp+0B0h+lpParam], rdi; lpParam
0x180076e47  mov     [rsp+0B0h+hInstance], rdi; hInstance
0x180076e4c  mov     [rsp+0B0h+hMenu], rdi; hMenu
0x180076e51  mov     [rsp+0B0h+hWndParent], rcx; hWndParent
0x180076e56  xor     ecx, ecx; dwExStyle
0x180076e58  mov     [rsp+0B0h+nHeight], edi; nHeight
0x180076e5c  mov     [rsp+0B0h+nWidth], edi; nWidth
0x180076e60  mov     [rsp+0B0h+Y], edi; Y
0x180076e64  mov     [rsp+0B0h+X], edi; X
0x180076e68  cmp     [r14+6Ch], di
0x180076e6d  jge     short loc_180076E84
0x180076e6f  movzx   edx, word ptr [rax+37Ch]; lpClassName
0x180076e76  lea     r8, pszFormat; lpWindowName
0x180076e7d  call    CreateWindowExW
0x180076e82  jmp     short loc_180076E97
0x180076e84  movzx   edx, word ptr [rax+37Ah]; lpClassName
0x180076e8b  lea     r8, byte_1800AB024; lpWindowName
0x180076e92  call    CreateWindowExA
0x180076e97  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180076e9e  mov     [rbp+37h+hWnd], rax
0x180076ea2  call    cs:__imp_RtlEnterCriticalSection
0x180076ea8  mov     r13, [rbp+37h+hWnd]
0x180076eac  test    r13, r13
0x180076eaf  jnz     short loc_180076EB8
0x180076eb1  xor     eax, eax
0x180076eb3  jmp     loc_1800770E3
0x180076eb8  mov     r15, [rbp+37h+arg_28]
0x180076ebc  mov     r8d, [r15]; int
0x180076ebf  lea     edx, [rdi+8]; int
0x180076ec2  xor     r9d, r9d; int
0x180076ec5  lea     r15, [r15+4]
0x180076ec9  mov     rcx, r13; HWND
0x180076ecc  call    ?_SetWindowLong@@YAJPEAUHWND__@@HJH@Z; _SetWindowLong(HWND__ *,int,long,int)
0x180076ed1  add     edi, 4
0x180076ed4  cmp     edi, 24h ; '$'
0x180076ed7  jb      short loc_180076EBC
0x180076ed9  mov     r15d, [rbp+37h+arg_38]
0x180076edd  xor     r9d, r9d; int
0x180076ee0  mov     rcx, [rbp+37h+hWnd]; HWND
0x180076ee4  mov     r8d, r15d; int
0x180076ee7  lea     edx, [r9+2Ch]; int
0x180076eeb  call    ?_SetWindowLong@@YAJPEAUHWND__@@HJH@Z; _SetWindowLong(HWND__ *,int,long,int)
0x180076ef0  mov     r8, [r14+8]; dwNewLong
0x180076ef4  mov     edx, 30h ; '0'; nIndex
0x180076ef9  mov     rcx, [rbp+37h+hWnd]; hWnd
0x180076efd  call    SetWindowLongPtrW
0x180076f02  mov     r8, [r14+10h]; dwNewLong
0x180076f06  mov     edx, 38h ; '8'; nIndex
0x180076f0b  mov     rcx, [rbp+37h+hWnd]; hWnd
0x180076f0f  call    SetWindowLongPtrW
0x180076f14  movzx   ecx, r12w; unsigned __int16
0x180076f18  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180076f1d  movzx   edi, [rbp+37h+arg_10]
0x180076f21  movzx   ecx, di; unsigned __int16
0x180076f24  movzx   r13d, ax
0x180076f28  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180076f2d  movzx   edx, ax
0x180076f30  shl     edx, 10h
0x180076f33  or      edx, r13d
0x180076f36  mov     [rbp+37h+arg_18], ax
0x180076f3a  mov     dword ptr [rbp+37h+var_38], edx
0x180076f3d  test    rbx, rbx
0x180076f40  jnz     short loc_180076F5F
0x180076f42  mov     rax, [rbp+37h+arg_20]
0x180076f46  mov     rcx, [rbp+37h+arg_30]
0x180076f4a  mov     [rbp+37h+hWnd+8], rax
0x180076f4e  mov     qword ptr [rbp+37h+var_38+8], rcx
0x180076f52  mov     word ptr [rbp+37h+var_38+4], r12w
0x180076f57  mov     word ptr [rbp+37h+var_38+6], di
0x180076f5b  mov     dword ptr [rbp+37h+var_28], r15d
0x180076f5f  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180076f66  call    cs:__imp_RtlLeaveCriticalSection
0x180076f6c  xor     r15d, r15d
0x180076f6f  test    rbx, rbx
0x180076f72  jz      short loc_180076FA9
0x180076f74  movsxd  r9, dword ptr [rbp+37h+var_38]; __int64
0x180076f78  lea     rax, [rbp+37h+var_50]
0x180076f7c  mov     r8, [rbp+37h+hWnd]; unsigned __int64
0x180076f80  mov     edx, 3E0h; unsigned int
0x180076f85  mov     [rsp+0B0h+nHeight], r15d; int
0x180076f8a  mov     rcx, rbx; HWND
0x180076f8d  mov     qword ptr [rsp+0B0h+nWidth], rax; unsigned __int64 *
0x180076f92  mov     [rsp+0B0h+Y], 3A98h; unsigned int
0x180076f9a  mov     [rsp+0B0h+X], 12h; unsigned int
0x180076fa2  call    ?SendMessageTimeoutWorker@@YA_JPEAUHWND__@@I_K_JIIPEA_KH@Z; SendMessageTimeoutWorker(HWND__ *,uint,unsigned __int64,__int64,uint,uint,unsigned __int64 *,int)
0x180076fa7  jmp     short loc_18007701E
0x180076fa9  lea     r9, szWindow; "NetDDE Agent"
0x180076fb0  xor     edx, edx; hWndChildAfter
0x180076fb2  lea     r8, szClass; "NDDEAgnt"
0x180076fb9  xor     ecx, ecx; hWndParent
0x180076fbb  call    FindWindowExW
0x180076fc0  test    rax, rax
0x180076fc3  jz      short loc_180076FF8
0x180076fc5  movsxd  r9, dword ptr [rbp+37h+var_38]; __int64
0x180076fc9  lea     rcx, [rbp+37h+var_50]
0x180076fcd  mov     r8, [rbp+37h+hWnd]; unsigned __int64
0x180076fd1  mov     edx, 3E0h; unsigned int
0x180076fd6  mov     [rsp+0B0h+nHeight], r15d; int
0x180076fdb  mov     qword ptr [rsp+0B0h+nWidth], rcx; unsigned __int64 *
0x180076fe0  mov     rcx, rax; HWND
0x180076fe3  mov     [rsp+0B0h+Y], 3A98h; unsigned int
0x180076feb  mov     [rsp+0B0h+X], 12h; unsigned int
0x180076ff3  call    ?SendMessageTimeoutWorker@@YA_JPEAUHWND__@@I_K_JIIPEA_KH@Z; SendMessageTimeoutWorker(HWND__ *,uint,unsigned __int64,__int64,uint,uint,unsigned __int64 *,int)
0x180076ff8  mov     [rsp+0B0h+nWidth], 1; int
0x180077000  lea     r9, [rbp+37h+hWnd]; __int64
0x180077004  mov     [rsp+0B0h+Y], r15d; int
0x180077009  lea     r8, ?InitiateEnumerationProc@@YAHPEAUHWND__@@PEAUtagINIT_ENUM@@@Z; int (*)(HWND, __int64)
0x180077010  xor     edx, edx; HWND
0x180077012  mov     [rsp+0B0h+X], r15d; unsigned int
0x180077017  xor     ecx, ecx; HDESK
0x180077019  call    ?EnumWindowsWorker@@YAHPEAUHDESK__@@PEAUHWND__@@P6AH1_J@Z2KHH@Z; EnumWindowsWorker(HDESK__ *,HWND__ *,int (*)(HWND__ *,__int64),__int64,ulong,int,int)
0x18007701e  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180077025  call    cs:__imp_RtlEnterCriticalSection
0x18007702b  movzx   ecx, r13w; nAtom
0x18007702f  call    cs:__imp_GlobalDeleteAtom
0x180077035  movzx   ecx, [rbp+37h+arg_18]; nAtom
0x180077039  call    cs:__imp_GlobalDeleteAtom
0x18007703f  mov     rcx, [rbp+37h+hWnd]; hWnd
0x180077043  xor     edx, edx; nIndex
0x180077045  call    GetWindowLongPtrW
0x18007704a  mov     rdi, rax
0x18007704d  test    rax, rax
0x180077050  jnz     short loc_18007707B
0x180077052  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180077059  call    cs:__imp_RtlLeaveCriticalSection
0x18007705f  mov     rcx, [rbp+37h+hWnd]
0x180077063  call    cs:__imp_NtUserDestroyWindow
0x180077069  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180077070  call    cs:__imp_RtlEnterCriticalSection
0x180077076  jmp     loc_180076EB1
0x18007707b  mov     rcx, [rbp+37h+hWnd]; HWND
0x18007707f  xor     r9d, r9d; int
0x180077082  xor     r8d, r8d; int
0x180077085  lea     edx, [r9+2Ch]; int
0x180077089  call    ?_SetWindowLong@@YAJPEAUHWND__@@HJH@Z; _SetWindowLong(HWND__ *,int,long,int)
0x18007708e  test    rbx, rbx
0x180077091  jz      short loc_1800770A5
0x180077093  movzx   ecx, r12w; unsigned __int16
0x180077097  mov     [rdi+70h], rbx
0x18007709b  mov     [rdi+3Ah], r12w
0x1800770a0  call    ?IncLocalAtomCount@@YAGG@Z; IncLocalAtomCount(ushort)
0x1800770a5  test    dword ptr [r14+18h], 40000000h
0x1800770ad  jz      short loc_1800770E0
0x1800770af  mov     rbx, rdi
0x1800770b2  mov     rax, [rbx+8]
0x1800770b6  test    dword ptr [rax+18h], 40000000h
0x1800770bd  jz      short loc_1800770D8
0x1800770bf  test    byte ptr [rbx+38h], 4
0x1800770c3  jz      short loc_1800770CB
0x1800770c5  test    byte ptr [rbx+38h], 10h
0x1800770c9  jz      short loc_1800770D8
0x1800770cb  mov     edx, 1; int
0x1800770d0  mov     rcx, rbx; struct tagCONV_INFO *
0x1800770d3  call    ?MonitorConv@@YAXPEAUtagCONV_INFO@@H@Z; MonitorConv(tagCONV_INFO *,int)
0x1800770d8  mov     rbx, [rbx]
0x1800770db  test    rbx, rbx
0x1800770de  jnz     short loc_1800770B2
0x1800770e0  mov     rax, rdi
0x1800770e3  lea     r11, [rsp+0B0h+var_20]
0x1800770eb  mov     rbx, [r11+30h]
0x1800770ef  mov     rdi, [r11+38h]
0x1800770f3  mov     rsp, r11
0x1800770f6  pop     r15
0x1800770f8  pop     r14
0x1800770fa  pop     r13
0x1800770fc  pop     r12
0x1800770fe  pop     rbp
0x1800770ff  retn
```
