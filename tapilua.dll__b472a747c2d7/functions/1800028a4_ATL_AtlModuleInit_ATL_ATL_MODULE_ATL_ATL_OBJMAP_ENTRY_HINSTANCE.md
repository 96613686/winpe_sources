# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x1800028a4`
- end: `0x180002a66`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004994`

## callees

- `0x1800028a4`
- `0x180006010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002997`
- `KERNEL32!DeleteCriticalSection` at `0x1800029a4`
- `KERNEL32!DeleteCriticalSection` at `0x180002a02`
- `KERNEL32!DeleteCriticalSection` at `0x180002997`
- `KERNEL32!DeleteCriticalSection` at `0x1800029a4`
- `KERNEL32!DeleteCriticalSection` at `0x180002a02`
- `KERNEL32!InitializeCriticalSection` at `0x1800028e9`
- `KERNEL32!InitializeCriticalSection` at `0x1800028f7`
- `KERNEL32!InitializeCriticalSection` at `0x180002905`
- `KERNEL32!InitializeCriticalSection` at `0x1800028e9`
- `KERNEL32!InitializeCriticalSection` at `0x1800028f7`
- `KERNEL32!InitializeCriticalSection` at `0x180002905`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax

  qword_18000A280 = (__int64)&off_18000A040;
  qword_18000A270 = a3;
  qword_18000A278 = a3;
  qword_18000A268 = a3;
  dword_18000A288 = 0;
  hHeap = 0;
  InitializeCriticalSection(&Buf1);
  InitializeCriticalSection(&stru_18000A2C0);
  InitializeCriticalSection(&CriticalSection);
  qword_18000A318 = 0;
  byte_18000A320 = 1;
  dword_18000A330 = 0;
  dword_18000A340 = 0;
  qword_18000A338 = 0;
  qword_18000A348 = 0;
  v4 = qword_18000A280;
  if ( qword_18000A280 )
  {
    while ( *(_QWORD *)v4 )
    {
      LOBYTE(v3) = 1;
      (*(void (__fastcall **)(__int64))(v4 + 64))(v3);
      v5 = 72;
      v3 = 56;
      if ( _Module == 176 )
        v5 = 56;
      v4 += v5;
    }
  }
  dword_18000A350 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800028a4  push    rbx
0x1800028a6  sub     rsp, 20h
0x1800028aa  lea     rax, off_18000A040
0x1800028b1  mov     cs:qword_18000A280, rax
0x1800028b8  mov     cs:qword_18000A270, r8
0x1800028bf  mov     cs:qword_18000A278, r8
0x1800028c6  mov     cs:qword_18000A268, r8
0x1800028cd  mov     cs:dword_18000A288, 0
0x1800028d7  mov     cs:hHeap, 0
0x1800028e2  lea     rcx, Buf1; lpCriticalSection
0x1800028e9  call    cs:__imp_InitializeCriticalSection
0x1800028ef  nop
0x1800028f0  lea     rcx, stru_18000A2C0; lpCriticalSection
0x1800028f7  call    cs:__imp_InitializeCriticalSection
0x1800028fd  nop
0x1800028fe  lea     rcx, CriticalSection; lpCriticalSection
0x180002905  call    cs:__imp_InitializeCriticalSection
0x18000290b  nop
0x18000290c  mov     cs:qword_18000A318, 0
0x180002917  mov     cs:byte_18000A320, 1
0x18000291e  mov     cs:dword_18000A330, 0
0x180002928  mov     cs:dword_18000A340, 0
0x180002932  mov     cs:qword_18000A338, 0
0x18000293d  mov     cs:qword_18000A348, 0
0x180002948  mov     rbx, cs:qword_18000A280
0x18000294f  test    rbx, rbx
0x180002952  jz      short loc_18000297F
0x180002954  jmp     short loc_180002979
0x180002956  mov     cl, 1
0x180002958  mov     rax, [rbx+40h]
0x18000295c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002961  mov     eax, 48h ; 'H'
0x180002966  lea     ecx, [rax-10h]
0x180002969  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180002973  cmovz   eax, ecx
0x180002976  add     rbx, rax
0x180002979  cmp     qword ptr [rbx], 0
0x18000297d  jnz     short loc_180002956
0x18000297f  mov     cs:dword_18000A350, 1
0x180002989  xor     eax, eax
0x18000298b  jmp     loc_180002A60
0x180002990  lea     rcx, stru_18000A2C0; lpCriticalSection
0x180002997  call    cs:__imp_DeleteCriticalSection
0x18000299d  lea     rcx, Buf1; lpCriticalSection
0x1800029a4  call    cs:__imp_DeleteCriticalSection
0x1800029aa  xorps   xmm0, xmm0
0x1800029ad  xor     eax, eax
0x1800029af  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x1800029b6  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x1800029bd  mov     cs:CriticalSection.SpinCount, rax
0x1800029c4  xorps   xmm1, xmm1
0x1800029c7  movups  xmmword ptr cs:stru_18000A2C0.DebugInfo, xmm1
0x1800029ce  movups  xmmword ptr cs:stru_18000A2C0.OwningThread, xmm1
0x1800029d5  mov     cs:stru_18000A2C0.SpinCount, rax
0x1800029dc  xorps   xmm0, xmm0
0x1800029df  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x1800029e6  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x1800029ed  mov     cs:Buf1.SpinCount, rax
0x1800029f4  mov     eax, 0C0000017h
0x1800029f9  jmp     short loc_180002A60
0x1800029fb  lea     rcx, Buf1; lpCriticalSection
0x180002a02  call    cs:__imp_DeleteCriticalSection
0x180002a08  xorps   xmm0, xmm0
0x180002a0b  xor     eax, eax
0x180002a0d  movups  xmmword ptr cs:stru_18000A2C0.DebugInfo, xmm0
0x180002a14  movups  xmmword ptr cs:stru_18000A2C0.OwningThread, xmm0
0x180002a1b  mov     cs:stru_18000A2C0.SpinCount, rax
0x180002a22  xorps   xmm1, xmm1
0x180002a25  movups  xmmword ptr cs:Buf1.DebugInfo, xmm1
0x180002a2c  movups  xmmword ptr cs:Buf1.OwningThread, xmm1
0x180002a33  mov     cs:Buf1.SpinCount, rax
0x180002a3a  mov     eax, 0C0000017h
0x180002a3f  jmp     short loc_180002A60
0x180002a41  xorps   xmm0, xmm0
0x180002a44  xor     eax, eax
0x180002a46  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x180002a4d  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x180002a54  mov     cs:Buf1.SpinCount, rax
0x180002a5b  mov     eax, 0C0000017h
0x180002a60  add     rsp, 20h
0x180002a64  pop     rbx
0x180002a65  retn
0x180005099  push    rbp
0x18000509b  sub     rsp, 20h
0x18000509f  mov     rbp, rdx
0x1800050a2  mov     rax, [rcx]
0x1800050a5  xor     ecx, ecx
0x1800050a7  cmp     dword ptr [rax], 0C0000017h
0x1800050ad  setz    cl
0x1800050b0  mov     eax, ecx
0x1800050b2  add     rsp, 20h
0x1800050b6  pop     rbp
0x1800050b7  retn
0x1800050b9  push    rbp
0x1800050bb  sub     rsp, 20h
0x1800050bf  mov     rbp, rdx
0x1800050c2  mov     rax, [rcx]
0x1800050c5  xor     ecx, ecx
0x1800050c7  cmp     dword ptr [rax], 0C0000017h
0x1800050cd  setz    cl
0x1800050d0  mov     eax, ecx
0x1800050d2  add     rsp, 20h
0x1800050d6  pop     rbp
0x1800050d7  retn
0x1800050d9  push    rbp
0x1800050db  sub     rsp, 20h
0x1800050df  mov     rbp, rdx
0x1800050e2  mov     rax, [rcx]
0x1800050e5  xor     ecx, ecx
0x1800050e7  cmp     dword ptr [rax], 0C0000017h
0x1800050ed  setz    cl
0x1800050f0  mov     eax, ecx
0x1800050f2  add     rsp, 20h
0x1800050f6  pop     rbp
0x1800050f7  retn
```
