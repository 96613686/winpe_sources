# Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(void)

- ea: `0x18000dd80`
- end: `0x18000de14`
- name: `?ProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@UEAAJXZ`
- size: `148`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceRelogger *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009fe4`
- `0x18000bef8`
- `0x18000dd80`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000dde4`
- `KERNEL32!GetCurrentThread` at `0x18000dde4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(
        Microsoft::Windows::Performance::CEventTraceRelogger *this)
{
  int v3; // r8d
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  void (__fastcall *v6[2])(HANDLE, _QWORD, _DWORD *, __int64); // [rsp+38h] [rbp-20h] BYREF
  int v7; // [rsp+48h] [rbp-10h]
  int v8; // [rsp+60h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 4) != 1 )
    return 2147947423LL;
  Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>((__int64)v6);
  v3 = Microsoft::Windows::Performance::CEventTraceRelogger::InternalProcessTraces(this);
  if ( v3 < 0 )
    *((_DWORD *)this + 4) = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 104LL))(
         *((_QWORD *)this + 3),
         (unsigned int)v3);
  if ( v6[0] )
  {
    v8 = v7;
    CurrentThread = GetCurrentThread();
    v6[0](CurrentThread, 0, &v8, 4);
  }
  return v4;
}

```

## disassembly

```asm
0x18000dd80  push    rbx
0x18000dd82  sub     rsp, 50h
0x18000dd86  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x18000dd8f  mov     rbx, rcx
0x18000dd92  cmp     dword ptr [rcx+10h], 1
0x18000dd96  jz      short loc_18000DD9F
0x18000dd98  mov     eax, 8007139Fh
0x18000dd9d  jmp     short loc_18000DE0D
0x18000dd9f  lea     rcx, [rsp+58h+var_20]
0x18000dda4  call    ??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)
0x18000dda9  mov     rcx, rbx; this
0x18000ddac  call    ?InternalProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEventTraceRelogger::InternalProcessTraces(void)
0x18000ddb1  mov     r8d, eax
0x18000ddb4  test    eax, eax
0x18000ddb6  jns     short loc_18000DDBF
0x18000ddb8  mov     dword ptr [rbx+10h], 0
0x18000ddbf  mov     rcx, [rbx+18h]
0x18000ddc3  mov     rdx, [rcx]
0x18000ddc6  mov     rax, [rdx+68h]
0x18000ddca  mov     edx, r8d
0x18000ddcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddd2  mov     ebx, eax
0x18000ddd4  cmp     [rsp+58h+var_20], 0
0x18000ddda  jz      short loc_18000DE0B
0x18000dddc  mov     ecx, [rsp+58h+var_10]
0x18000dde0  mov     [rsp+58h+arg_0], ecx
0x18000dde4  call    cs:__imp_GetCurrentThread
0x18000ddeb  nop     dword ptr [rax+rax+00h]
0x18000ddf0  mov     rcx, rax
0x18000ddf3  mov     r9d, 4
0x18000ddf9  lea     r8, [rsp+58h+arg_0]
0x18000ddfe  xor     edx, edx
0x18000de00  mov     rax, [rsp+58h+var_20]
0x18000de05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0a  nop
0x18000de0b  mov     eax, ebx
0x18000de0d  add     rsp, 50h
0x18000de11  pop     rbx
0x18000de12  retn
```
