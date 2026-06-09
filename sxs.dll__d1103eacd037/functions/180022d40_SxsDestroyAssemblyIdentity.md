# SxsDestroyAssemblyIdentity

- ea: `0x180022d40`
- end: `0x180022f50`
- name: `SxsDestroyAssemblyIdentity`
- size: `528`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `29`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800072dc`
- `0x1800075c0`
- `0x18000d4d0`
- `0x18000e160`
- `0x18000f170`
- `0x180010bd0`
- `0x180010e20`
- `0x180011de0`
- `0x180013f4c`
- `0x1800159c4`
- `0x180020e20`
- `0x180021150`
- `0x18002b4c0`
- `0x18002b580`
- `0x18002bdb4`
- `0x180040a30`
- `0x180041f10`
- `0x1800426f0`
- `0x180053f58`
- `0x180053fd0`
- `0x1800548fc`
- `0x180058150`
- `0x180058284`
- `0x18005ae60`
- `0x180060390`
- `0x180061664`
- `0x1800616f0`
- `0x180061f6c`
- `0x180065700`

## callees

- `0x18001c2c8`
- `0x180022d40`
- `0x180022f60`
- `0x18005cf40`
- `0x180069c88`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180022ef0`
- `ntdll!RtlPopFrame` at `0x180022ef0`
- `ntdll!RtlPushFrame` at `0x180022d99`
- `ntdll!RtlPushFrame` at `0x180022d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022db2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022ece`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022ece`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022e36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ec0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022e36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ec0`

## pseudocode

```c
void __fastcall SxsDestroyAssemblyIdentity(_QWORD *lpMem)
{
  DWORD LastError; // ebx
  __int64 v3; // rdi
  char *v4; // r12
  unsigned int v5; // r13d
  unsigned int v6; // r14d
  _QWORD *v7; // r15
  volatile signed __int32 *v8; // r8
  _QWORD *v9; // rsi
  unsigned int i; // esi
  const struct _ASSEMBLY_IDENTITY_NAMESPACE **v11; // rdi
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h]
  int v14; // [rsp+40h] [rbp-38h]

  if ( lpMem )
  {
    Frame.Flags = 1;
    Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D4C0;
    Frame.Previous = 0;
    v13 = 544438355;
    v14 = 1501;
    RtlPushFrame(&Frame);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    LastError = GetLastError();
    if ( (*((_BYTE *)lpMem + 4) & 2) == 0 )
    {
      v3 = 0;
      v4 = (char *)lpMem[6];
      v5 = *((_DWORD *)lpMem + 6);
      v6 = *((_DWORD *)lpMem + 4);
      v7 = (_QWORD *)lpMem[5];
      if ( v6 )
      {
        do
        {
          v8 = (volatile signed __int32 *)v7[v3];
          v9 = &v7[v3];
          if ( v8 && _InterlockedExchangeAdd(v8 + 18, 0xFFFFFFFF) == 1 )
            HeapFree(g_hHeap, 0, (LPVOID)v8);
          v3 = (unsigned int)(v3 + 1);
          *v9 = 0;
        }
        while ( (unsigned int)v3 < v6 );
      }
      for ( i = 0; i < v5; *v11 = 0 )
      {
        v11 = (const struct _ASSEMBLY_IDENTITY_NAMESPACE **)&v4[8 * i];
        SxspDeallocateAssemblyIdentityNamespace(*v11);
        ++i;
      }
      if ( (*((_BYTE *)lpMem + 4) & 1) != 0 )
      {
        operator delete(v7);
        lpMem[5] = 0;
      }
      if ( (*((_BYTE *)lpMem + 4) & 4) != 0 )
      {
        if ( v4 )
          HeapFree(g_hHeap, 0, v4);
        lpMem[6] = 0;
      }
    }
    HeapFree(g_hHeap, 0, lpMem);
    SetLastError(LastError);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallExit();
    RtlPopFrame(&Frame);
  }
}

```

## disassembly

```asm
0x180022d40  test    rcx, rcx
0x180022d43  jnz     short loc_180022D47
0x180022d45  retn
0x180022d47  push    rbp
0x180022d48  sub     rsp, 70h
0x180022d4c  mov     rax, cs:__security_cookie
0x180022d53  xor     rax, rsp
0x180022d56  mov     [rsp+78h+var_30], rax
0x180022d5b  mov     rbp, rcx
0x180022d5e  mov     [rsp+78h+arg_8], rbx
0x180022d66  lea     rax, qword_18006D4C0
0x180022d6d  mov     [rsp+78h+Frame.Flags], 1
0x180022d75  lea     rcx, [rsp+78h+Frame]; Frame
0x180022d7a  mov     [rsp+78h+Frame.Context], rax
0x180022d7f  mov     [rsp+78h+Frame.Previous], 0
0x180022d88  mov     [rsp+78h+var_40], 20737853h
0x180022d91  mov     [rsp+78h+var_38], 5DDh
0x180022d99  call    cs:__imp_RtlPushFrame
0x180022da0  nop     dword ptr [rax+rax+00h]
0x180022da5  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180022dac  jnz     loc_180022F10
0x180022db2  call    cs:__imp_GetLastError
0x180022db9  nop     dword ptr [rax+rax+00h]
0x180022dbe  test    byte ptr [rbp+4], 2
0x180022dc2  mov     ebx, eax
0x180022dc4  jnz     loc_180022EB4
0x180022dca  mov     [rsp+78h+arg_10], rsi
0x180022dd2  mov     [rsp+78h+arg_18], rdi
0x180022dda  xor     edi, edi
0x180022ddc  mov     [rsp+78h+var_10], r12
0x180022de1  mov     r12, [rbp+30h]
0x180022de5  mov     [rsp+78h+var_18], r13
0x180022dea  mov     r13d, [rbp+18h]
0x180022dee  mov     [rsp+78h+var_20], r14
0x180022df3  mov     r14d, [rbp+10h]
0x180022df7  mov     [rsp+78h+var_28], r15
0x180022dfc  mov     r15, [rbp+28h]
0x180022e00  test    r14d, r14d
0x180022e03  jz      short loc_180022E50
0x180022e05  nop     word ptr [rax+rax+00000000h]
0x180022e10  mov     r8, [r15+rdi*8]; lpMem
0x180022e14  lea     rsi, [r15+rdi*8]
0x180022e18  test    r8, r8
0x180022e1b  jz      short loc_180022E42
0x180022e1d  mov     eax, 0FFFFFFFFh
0x180022e22  lock xadd [r8+48h], eax
0x180022e28  cmp     eax, 1
0x180022e2b  jnz     short loc_180022E42
0x180022e2d  mov     rcx, cs:g_hHeap; hHeap
0x180022e34  xor     edx, edx; dwFlags
0x180022e36  call    cs:__imp_HeapFree
0x180022e3d  nop     dword ptr [rax+rax+00h]
0x180022e42  inc     edi
0x180022e44  mov     qword ptr [rsi], 0
0x180022e4b  cmp     edi, r14d
0x180022e4e  jb      short loc_180022E10
0x180022e50  xor     r14d, r14d
0x180022e53  mov     esi, r14d
0x180022e56  test    r13d, r13d
0x180022e59  jnz     loc_180022F1A
0x180022e5f  test    byte ptr [rbp+4], 1
0x180022e63  mov     r13, [rsp+78h+var_18]
0x180022e68  mov     rdi, [rsp+78h+arg_18]
0x180022e70  mov     rsi, [rsp+78h+arg_10]
0x180022e78  jnz     loc_180022F38
0x180022e7e  test    byte ptr [rbp+4], 4
0x180022e82  mov     r15, [rsp+78h+var_28]
0x180022e87  jz      short loc_180022EAA
0x180022e89  test    r12, r12
0x180022e8c  jz      short loc_180022EA6
0x180022e8e  mov     rcx, cs:g_hHeap; hHeap
0x180022e95  mov     r8, r12; lpMem
0x180022e98  xor     edx, edx; dwFlags
0x180022e9a  call    cs:__imp_HeapFree
0x180022ea1  nop     dword ptr [rax+rax+00h]
0x180022ea6  mov     [rbp+30h], r14
0x180022eaa  mov     r12, [rsp+78h+var_10]
0x180022eaf  mov     r14, [rsp+78h+var_20]
0x180022eb4  mov     rcx, cs:g_hHeap; hHeap
0x180022ebb  mov     r8, rbp; lpMem
0x180022ebe  xor     edx, edx; dwFlags
0x180022ec0  call    cs:__imp_HeapFree
0x180022ec7  nop     dword ptr [rax+rax+00h]
0x180022ecc  mov     ecx, ebx; dwErrCode
0x180022ece  call    cs:__imp_SetLastError
0x180022ed5  nop     dword ptr [rax+rax+00h]
0x180022eda  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180022ee1  mov     rbx, [rsp+78h+arg_8]
0x180022ee9  jnz     short loc_180022F49
0x180022eeb  lea     rcx, [rsp+78h+Frame]; Frame
0x180022ef0  call    cs:__imp_RtlPopFrame
0x180022ef7  nop     dword ptr [rax+rax+00h]
0x180022efc  mov     rcx, [rsp+78h+var_30]
0x180022f01  xor     rcx, rsp; StackCookie
0x180022f04  call    __security_check_cookie
0x180022f09  add     rsp, 70h
0x180022f0d  pop     rbp
0x180022f0e  retn
0x180022f10  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180022f15  jmp     loc_180022DB2
0x180022f1a  mov     eax, esi
0x180022f1c  mov     rcx, [r12+rax*8]; lpMem
0x180022f20  lea     rdi, [r12+rax*8]
0x180022f24  call    ?SxspDeallocateAssemblyIdentityNamespace@@YAXPEBU_ASSEMBLY_IDENTITY_NAMESPACE@@@Z; SxspDeallocateAssemblyIdentityNamespace(_ASSEMBLY_IDENTITY_NAMESPACE const *)
0x180022f29  inc     esi
0x180022f2b  mov     [rdi], r14
0x180022f2e  cmp     esi, r13d
0x180022f31  jb      short loc_180022F1A
0x180022f33  jmp     loc_180022E5F
0x180022f38  mov     rcx, r15; void *
0x180022f3b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022f40  mov     [rbp+28h], r14
0x180022f44  jmp     loc_180022E7E
0x180022f49  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x180022f4e  jmp     short loc_180022EEB
```
