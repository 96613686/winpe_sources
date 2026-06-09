# CEcsReadOpLock::CEcsReadOpLock(void)

- ea: `0x1800d0f74`
- end: `0x1800d10da`
- name: `??0CEcsReadOpLock@@QEAA@XZ`
- size: `358`
- prototype: `CEcsReadOpLock *__fastcall(CEcsReadOpLock *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800d0d9c`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x1800110fc`
- `0x180011314`
- `0x1800d0f74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d10b0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d10b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d1056`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d1056`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800d0fb7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800d0fb7`

## string_xrefs

- `0x1800d101c`: `CEcsReadOpLock::CEcsReadOpLock`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CEcsReadOpLock *__fastcall CEcsReadOpLock::CEcsReadOpLock(CEcsReadOpLock *this)
{
  HANDLE *v2; // rdi
  _BYTE *v3; // rax
  char v4; // cl
  int v6; // [rsp+20h] [rbp-20h] BYREF
  int v7; // [rsp+24h] [rbp-1Ch]
  char v8; // [rsp+28h] [rbp-18h]
  const char *v9; // [rsp+30h] [rbp-10h]
  __int64 v10; // [rsp+38h] [rbp-8h]
  HANDLE pExceptionObject; // [rsp+58h] [rbp+18h] BYREF

  *(_QWORD *)this = &CEcsReadOpLock::`vftable';
  *((_QWORD *)this + 1) = -1;
  v2 = (HANDLE *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( (v3[68] & 2) != 0 && v3[65] >= 6u )
  {
    v4 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v4 = 0;
LABEL_9:
  v6 = 0;
  v7 = 14;
  v8 = v4;
  v9 = "CEcsReadOpLock::CEcsReadOpLock";
  v10 = 0;
  *((_OWORD *)this + 2) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *(_OWORD *)((char *)this + 76) = 0;
  *(_QWORD *)((char *)this + 92) = 0;
  pExceptionObject = CreateEventW(0, 1, 0, 0);
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(v2, &pExceptionObject);
  if ( !*v2 )
  {
    HIWORD(v7) = 21;
    LODWORD(pExceptionObject) = EcsGetLastFailureAsHRESULT();
    throw (long *)&pExceptionObject;
  }
  v6 = 0;
  LOWORD(v7) = 21;
  SetEvent(*v2);
  *((_BYTE *)this + 144) = 0;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v6);
  return this;
}

```

## disassembly

```asm
0x1800d0f74  mov     [rsp-8+arg_10], rbx
0x1800d0f79  mov     [rsp-8+arg_18], rdi
0x1800d0f7e  mov     [rsp-8+arg_0], rcx
0x1800d0f83  push    rbp
0x1800d0f84  mov     rbp, rsp
0x1800d0f87  sub     rsp, 40h
0x1800d0f8b  mov     rbx, rcx
0x1800d0f8e  lea     rax, ??_7CEcsReadOpLock@@6B@; const CEcsReadOpLock::`vftable'
0x1800d0f95  mov     [rcx], rax
0x1800d0f98  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x1800d0fa0  lea     rdi, [rcx+10h]
0x1800d0fa4  mov     qword ptr [rdi], 0
0x1800d0fab  mov     qword ptr [rcx+18h], 0
0x1800d0fb3  add     rcx, 68h ; 'h'; lpCriticalSection
0x1800d0fb7  call    cs:__imp_InitializeCriticalSection
0x1800d0fbd  nop
0x1800d0fbe  lea     rcx, WPP_GLOBAL_Control
0x1800d0fc5  mov     rax, cs:WPP_GLOBAL_Control
0x1800d0fcc  cmp     rax, rcx
0x1800d0fcf  jz      short loc_1800D0FF9
0x1800d0fd1  test    byte ptr [rax+44h], 2
0x1800d0fd5  jz      short loc_1800D1009
0x1800d0fd7  cmp     byte ptr [rax+41h], 6
0x1800d0fdb  jb      short loc_1800D0FF9
0x1800d0fdd  mov     edx, 0Ah
0x1800d0fe2  lea     r8, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids
0x1800d0fe9  mov     rcx, [rax+38h]
0x1800d0fed  call    WPP_SF_
0x1800d0ff2  mov     rax, cs:WPP_GLOBAL_Control
0x1800d0ff9  test    byte ptr [rax+44h], 2
0x1800d0ffd  jz      short loc_1800D1009
0x1800d0fff  cmp     byte ptr [rax+41h], 6
0x1800d1003  jb      short loc_1800D1009
0x1800d1005  mov     cl, 1
0x1800d1007  jmp     short loc_1800D100B
0x1800d1009  xor     cl, cl
0x1800d100b  mov     [rbp+var_20], 0
0x1800d1012  mov     [rbp+var_1C], 0Eh
0x1800d1019  mov     [rbp+var_18], cl
0x1800d101c  lea     rax, aCecsreadoplock; "CEcsReadOpLock::CEcsReadOpLock"
0x1800d1023  mov     [rbp+var_10], rax
0x1800d1027  mov     [rbp+var_8], 0
0x1800d102f  xorps   xmm0, xmm0
0x1800d1032  movups  xmmword ptr [rbx+20h], xmm0
0x1800d1036  movups  xmmword ptr [rbx+30h], xmm0
0x1800d103a  xor     eax, eax
0x1800d103c  mov     [rbx+40h], rax
0x1800d1040  mov     [rbx+48h], eax
0x1800d1043  movups  xmmword ptr [rbx+4Ch], xmm0
0x1800d1047  mov     [rbx+5Ch], rax
0x1800d104b  xor     r9d, r9d; lpName
0x1800d104e  xor     r8d, r8d; bInitialState
0x1800d1051  lea     edx, [rax+1]; bManualReset
0x1800d1054  xor     ecx, ecx; lpEventAttributes
0x1800d1056  call    cs:__imp_CreateEventW
0x1800d105c  mov     [rbp+pExceptionObject], rax
0x1800d1060  lea     rdx, [rbp+pExceptionObject]
0x1800d1064  mov     rcx, rdi
0x1800d1067  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x1800d106c  mov     eax, [rbp+var_20]
0x1800d106f  mov     [rbp+var_20], eax
0x1800d1072  cmp     qword ptr [rdi], 0
0x1800d1076  jnz     short loc_1800D109D
0x1800d1078  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800d107d  mov     [rbp+var_20], eax
0x1800d1080  mov     ecx, 15h
0x1800d1085  mov     word ptr [rbp+var_1C+2], cx
0x1800d1089  mov     dword ptr [rbp+pExceptionObject], eax
0x1800d108c  lea     rdx, _TI1J; pThrowInfo
0x1800d1093  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d1097  call    _CxxThrowException_0
0x1800d109d  mov     [rbp+var_20], 0
0x1800d10a4  mov     ecx, 15h
0x1800d10a9  mov     word ptr [rbp+var_1C], cx
0x1800d10ad  mov     rcx, [rdi]; hEvent
0x1800d10b0  call    cs:__imp_SetEvent
0x1800d10b6  mov     byte ptr [rbx+90h], 0
0x1800d10bd  lea     rcx, [rbp+var_20]; this
0x1800d10c1  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800d10c6  nop
0x1800d10c7  mov     rax, rbx
0x1800d10ca  mov     rbx, [rsp+40h+arg_10]
0x1800d10cf  mov     rdi, [rsp+40h+arg_18]
0x1800d10d4  add     rsp, 40h
0x1800d10d8  pop     rbp
0x1800d10d9  retn
```
