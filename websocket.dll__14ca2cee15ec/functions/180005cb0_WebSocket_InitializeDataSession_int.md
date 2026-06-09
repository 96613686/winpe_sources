# WebSocket::InitializeDataSession(int)

- ea: `0x180005cb0`
- end: `0x180005fd5`
- name: `?InitializeDataSession@WebSocket@@AEAAJH@Z`
- size: `805`
- prototype: `__int64 __fastcall(WebSocket *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002320`
- `0x1800023b0`

## callees

- `0x180001234`
- `0x180001274`
- `0x180005cb0`
- `0x180009350`
- `0x18000a3c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005d24`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005d2e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005d38`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005d24`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005d2e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005d38`

## pseudocode

```c
__int64 __fastcall WebSocket::InitializeDataSession(WebSocket *this, int a2)
{
  void *v2; // rbx
  void *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  unsigned int v8; // ebx
  int *v9; // r14
  bool v10; // zf
  int *v11; // r15
  struct _RTL_CRITICAL_SECTION_DEBUG *v12; // r8
  int v13; // ecx
  int v14; // edx
  __int64 v15; // rdx
  unsigned int v16; // ecx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    ClientHandshakeProcessor::~ClientHandshakeProcessor(*((ClientHandshakeProcessor **)this + 1));
    operator delete(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    ServerHandshakeProcessor::~ServerHandshakeProcessor(*((ServerHandshakeProcessor **)this + 2));
    operator delete(v5);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)operator new(0x1C0u);
  v7 = v6;
  if ( v6 )
  {
    InitializeCriticalSection(v6);
    InitializeCriticalSection(v7 + 1);
    InitializeCriticalSection(v7 + 2);
    v7[3].DebugInfo = 0;
    *(_QWORD *)&v7[3].LockCount = 0;
    LODWORD(v7[3].OwningThread) = 0;
    v7[3].LockSemaphore = 0;
    v7[3].SpinCount = 0;
    LODWORD(v7[4].DebugInfo) = 0;
    *(_QWORD *)&v7[4].LockCount = 0;
    v7[4].OwningThread = 0;
    LODWORD(v7[4].LockSemaphore) = 0;
    v7[4].SpinCount = 0;
    v7[5].DebugInfo = 0;
    v7[5].LockCount = 0;
    *(_QWORD *)&v7[6].RecursionCount = 0;
    *(HANDLE *)((char *)&v7[6].OwningThread + 4) = 0;
    HIDWORD(v7[6].LockSemaphore) = 0;
    v7[5].SpinCount = 0;
    LOBYTE(v7[6].SpinCount) = 0;
    v7[7].DebugInfo = 0;
    *(_QWORD *)&v7[7].LockCount = 0;
    v7[7].OwningThread = 0;
    LODWORD(v7[7].LockSemaphore) = 0;
    v7[5].LockSemaphore = 0;
    v7[8].SpinCount = 0;
    HIDWORD(v7[7].LockSemaphore) = -1;
    LODWORD(v7[7].SpinCount) = -1;
    v7[8].OwningThread = HANDLE_FLAG_INHERIT;
    LODWORD(v7[5].OwningThread) = 0;
    LODWORD(v7[8].LockSemaphore) = 1;
    LODWORD(v7[8].DebugInfo) = 1;
    HIDWORD(v7[7].SpinCount) = 0;
    *(PRTL_CRITICAL_SECTION_DEBUG *)((char *)&v7[8].DebugInfo + 4) = 0;
    v7[8].RecursionCount = 0;
    v7[9].LockSemaphore = &v7[9].OwningThread;
    v7[9].OwningThread = &v7[9].OwningThread;
    v7[10].OwningThread = &v7[10].LockCount;
    *(_QWORD *)&v7[10].LockCount = (char *)v7 + 408;
    v7[10].LockSemaphore = 0;
    *(_QWORD *)&v7[9].LockCount = v7 + 9;
    v7[9].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&v7[9];
    HIDWORD(v7[9].SpinCount) = -2147483646;
    LODWORD(v7[9].SpinCount) = 0;
    LODWORD(v7[10].DebugInfo) = 0;
    v7[10].SpinCount = 0;
    LODWORD(v7[11].DebugInfo) = 0;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 3) = v7;
  if ( !v7 )
    return (unsigned int)-2147024882;
  v9 = (int *)*((_QWORD *)this + 4);
  LODWORD(v7[8].OwningThread) = a2;
  v10 = *((_QWORD *)v9 + 2) == 0;
  LODWORD(v7[8].DebugInfo) = 1;
  v11 = v9 + 1;
  HIDWORD(v7[8].LockSemaphore) = v10;
  v12 = (struct _RTL_CRITICAL_SECTION_DEBUG *)*((_QWORD *)v9 + 2);
  if ( v12 )
  {
    v8 = 0;
  }
  else
  {
    v13 = *v11;
    v14 = *v9;
    if ( *v9 > (unsigned int)~*v11
      || (unsigned int)(v14 + v13) > 0xFFFFFFEF
      || (unsigned int)(v14 + v13 + 16) > 0xFFFFFF7F
      || (unsigned int)(v14 + v13 + 144) > 0xFFFFFFF8 )
    {
      return (unsigned int)-2147024362;
    }
    v8 = 0;
    v12 = (struct _RTL_CRITICAL_SECTION_DEBUG *)operator new(
                                                  saturated_mul(
                                                    (unsigned __int64)(unsigned int)(v14 + v13 + 151) >> 3,
                                                    8u));
  }
  v7[8].SpinCount = (ULONG_PTR)v12;
  if ( v12 )
  {
    v7[3].LockCount = *v9;
    v7[3].DebugInfo = v12;
    *(_QWORD *)&v7[3].RecursionCount = 0;
    v15 = (unsigned int)*v9;
    LODWORD(v7[3].SpinCount) = *v11;
    *(ULONG_PTR *)((char *)&v7[3].SpinCount + 4) = 0;
    v7[3].LockSemaphore = (char *)v12 + v15;
    v16 = v15 + *v11;
    v7[5].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)128;
    v7[5].LockCount = 0;
    v7[4].OwningThread = (HANDLE)16;
    LODWORD(v7[4].LockSemaphore) = 0;
    v7[4].SpinCount = (ULONG_PTR)v12 + v16;
    *(_QWORD *)&v7[4].LockCount = (char *)v12 + v16 + 128;
    v7[8].RecursionCount = *v9;
    HIDWORD(v7[8].OwningThread) = v9[2];
    LODWORD(v7[8].LockSemaphore) = v9[3] == 0;
    operator delete(*((void **)this + 4));
    *((_QWORD *)this + 4) = 0;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x180005cb0  push    rbx
0x180005cb2  push    rbp
0x180005cb3  push    rsi
0x180005cb4  push    rdi
0x180005cb5  push    r12
0x180005cb7  push    r13
0x180005cb9  push    r14
0x180005cbb  push    r15
0x180005cbd  sub     rsp, 28h
0x180005cc1  mov     rbx, [rcx+8]
0x180005cc5  xor     r12d, r12d
0x180005cc8  mov     ebp, edx
0x180005cca  mov     rsi, rcx
0x180005ccd  test    rbx, rbx
0x180005cd0  jz      short loc_180005CE6
0x180005cd2  mov     rcx, rbx; this
0x180005cd5  call    ??1ClientHandshakeProcessor@@QEAA@XZ; ClientHandshakeProcessor::~ClientHandshakeProcessor(void)
0x180005cda  mov     rcx, rbx; Block
0x180005cdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005ce2  mov     [rsi+8], r12
0x180005ce6  mov     rbx, [rsi+10h]
0x180005cea  test    rbx, rbx
0x180005ced  jz      short loc_180005D03
0x180005cef  mov     rcx, rbx; this
0x180005cf2  call    ??1ServerHandshakeProcessor@@QEAA@XZ; ServerHandshakeProcessor::~ServerHandshakeProcessor(void)
0x180005cf7  mov     rcx, rbx; Block
0x180005cfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005cff  mov     [rsi+10h], r12
0x180005d03  mov     ecx, 1C0h; Size
0x180005d08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d0d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180005d11  mov     rdi, rax
0x180005d14  lea     r15d, [r13+2]
0x180005d18  test    rax, rax
0x180005d1b  jz      loc_180005E65
0x180005d21  mov     rcx, rax; lpCriticalSection
0x180005d24  call    cs:__imp_InitializeCriticalSection
0x180005d2a  lea     rcx, [rdi+28h]; lpCriticalSection
0x180005d2e  call    cs:__imp_InitializeCriticalSection
0x180005d34  lea     rcx, [rdi+50h]; lpCriticalSection
0x180005d38  call    cs:__imp_InitializeCriticalSection
0x180005d3e  mov     [rdi+78h], r12
0x180005d42  lea     rcx, [rdi+168h]
0x180005d49  mov     [rdi+80h], r12
0x180005d50  lea     rax, [rcx+10h]
0x180005d54  mov     [rdi+88h], r12d
0x180005d5b  mov     [rdi+90h], r12
0x180005d62  mov     [rdi+98h], r12
0x180005d69  mov     [rdi+0A0h], r12d
0x180005d70  mov     [rdi+0A8h], r12
0x180005d77  mov     [rdi+0B0h], r12
0x180005d7e  mov     [rdi+0B8h], r12d
0x180005d85  mov     [rdi+0C0h], r12
0x180005d8c  mov     [rdi+0C8h], r12
0x180005d93  mov     [rdi+0D0h], r12d
0x180005d9a  mov     [rdi+0FCh], r12
0x180005da1  mov     [rdi+104h], r12
0x180005da8  mov     [rdi+10Ch], r12d
0x180005daf  mov     [rdi+0E8h], r12
0x180005db6  mov     [rdi+110h], r12b
0x180005dbd  mov     [rdi+118h], r12
0x180005dc4  mov     [rdi+120h], r12
0x180005dcb  mov     [rdi+128h], r12
0x180005dd2  mov     [rdi+130h], r12d
0x180005dd9  mov     [rdi+0E0h], r12
0x180005de0  mov     [rdi+160h], r12
0x180005de7  mov     [rdi+134h], r13d
0x180005dee  mov     [rdi+138h], r13d
0x180005df5  mov     [rdi+150h], r15
0x180005dfc  mov     [rdi+0D8h], r12d
0x180005e03  mov     [rdi+158h], r15d
0x180005e0a  mov     [rdi+140h], r15d
0x180005e11  mov     [rdi+13Ch], r12d
0x180005e18  mov     [rdi+144h], r12
0x180005e1f  mov     [rdi+14Ch], r12d
0x180005e26  mov     [rax+8], rax
0x180005e2a  mov     [rax], rax
0x180005e2d  lea     rax, [rdi+198h]
0x180005e34  mov     [rax+8], rax
0x180005e38  mov     [rax], rax
0x180005e3b  mov     [rax+10h], r12
0x180005e3f  mov     [rcx+8], rcx
0x180005e43  mov     [rcx], rcx
0x180005e46  mov     dword ptr [rcx+24h], 80000002h
0x180005e4d  mov     [rcx+20h], r12d
0x180005e51  mov     [rcx+28h], r12d
0x180005e55  mov     [rdi+1B0h], r12
0x180005e5c  mov     [rdi+1B8h], r12d
0x180005e63  jmp     short loc_180005E68
0x180005e65  mov     rdi, r12
0x180005e68  mov     [rsi+18h], rdi
0x180005e6c  test    rdi, rdi
0x180005e6f  jnz     short loc_180005E7B
0x180005e71  mov     ebx, 8007000Eh
0x180005e76  jmp     loc_180005FC2
0x180005e7b  mov     r14, [rsi+20h]
0x180005e7f  mov     eax, r12d
0x180005e82  mov     [rdi+150h], ebp
0x180005e88  cmp     [r14+10h], r12
0x180005e8c  mov     [rdi+140h], r15d
0x180005e93  lea     r15, [r14+4]
0x180005e97  setz    al
0x180005e9a  mov     [rdi+15Ch], eax
0x180005ea0  mov     r8, [r14+10h]
0x180005ea4  test    r8, r8
0x180005ea7  jz      short loc_180005EAE
0x180005ea9  mov     ebx, r12d
0x180005eac  jmp     short loc_180005F07
0x180005eae  mov     ecx, [r15]
0x180005eb1  mov     eax, ecx
0x180005eb3  mov     edx, [r14]
0x180005eb6  not     eax
0x180005eb8  cmp     edx, eax
0x180005eba  ja      loc_180005FBD
0x180005ec0  lea     eax, [rdx+rcx]
0x180005ec3  cmp     eax, 0FFFFFFEFh
0x180005ec6  ja      loc_180005FBD
0x180005ecc  add     eax, 10h
0x180005ecf  cmp     eax, 0FFFFFF7Fh
0x180005ed4  ja      loc_180005FBD
0x180005eda  sub     eax, 0FFFFFF80h
0x180005edd  cmp     eax, 0FFFFFFF8h
0x180005ee0  ja      loc_180005FBD
0x180005ee6  lea     ecx, [rax+7]
0x180005ee9  mov     ebx, r12d
0x180005eec  shr     rcx, 3
0x180005ef0  mov     eax, 8
0x180005ef5  mul     rcx
0x180005ef8  cmovb   rax, r13
0x180005efc  mov     rcx, rax; Size
0x180005eff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f04  mov     r8, rax
0x180005f07  mov     [rdi+160h], r8
0x180005f0e  test    r8, r8
0x180005f11  jz      loc_180005E71
0x180005f17  mov     eax, [r14]
0x180005f1a  mov     [rdi+80h], eax
0x180005f20  mov     [rdi+78h], r8
0x180005f24  mov     [rdi+84h], r12
0x180005f2b  mov     edx, [r14]
0x180005f2e  mov     ecx, [r15]
0x180005f31  mov     [rdi+98h], ecx
0x180005f37  mov     [rdi+9Ch], r12
0x180005f3e  lea     rax, [r8+rdx]
0x180005f42  mov     [rdi+90h], rax
0x180005f49  mov     ecx, [r15]
0x180005f4c  add     ecx, edx
0x180005f4e  mov     qword ptr [rdi+0C8h], 80h
0x180005f59  mov     [rdi+0D0h], r12d
0x180005f60  mov     qword ptr [rdi+0B0h], 10h
0x180005f6b  mov     [rdi+0B8h], r12d
0x180005f72  mov     eax, ecx
0x180005f74  sub     ecx, 0FFFFFF80h
0x180005f77  add     rax, r8
0x180005f7a  add     rcx, r8
0x180005f7d  mov     [rdi+0C0h], rax
0x180005f84  mov     [rdi+0A8h], rcx
0x180005f8b  mov     eax, [r14]
0x180005f8e  mov     [rdi+14Ch], eax
0x180005f94  mov     eax, [r14+8]
0x180005f98  mov     [rdi+154h], eax
0x180005f9e  mov     eax, r12d
0x180005fa1  cmp     [r14+0Ch], r12d
0x180005fa5  setz    al
0x180005fa8  mov     [rdi+158h], eax
0x180005fae  mov     rcx, [rsi+20h]; Block
0x180005fb2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005fb7  mov     [rsi+20h], r12
0x180005fbb  jmp     short loc_180005FC2
0x180005fbd  mov     ebx, 80070216h
0x180005fc2  mov     eax, ebx
0x180005fc4  add     rsp, 28h
0x180005fc8  pop     r15
0x180005fca  pop     r14
0x180005fcc  pop     r13
0x180005fce  pop     r12
0x180005fd0  pop     rdi
0x180005fd1  pop     rsi
0x180005fd2  pop     rbp
0x180005fd3  pop     rbx
0x180005fd4  retn
```
