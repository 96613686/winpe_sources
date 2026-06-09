# CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)

- ea: `0x140013b00`
- end: `0x140013c4e`
- name: `??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z`
- size: `334`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `522`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400037bc`
- `0x140008f7c`
- `0x1400090d0`
- `0x140009b50`
- `0x140009ea0`
- `0x14000a988`
- `0x14000ac50`
- `0x14000c84c`
- `0x14000e670`
- `0x14000fba0`
- `0x14001cafc`
- `0x14001d750`
- `0x14001e91c`
- `0x140024500`
- `0x1400272d8`
- `0x140027420`
- `0x14002e39c`
- `0x14002e580`
- `0x1400330fc`
- `0x140035f90`
- `0x140036788`
- `0x1400369ec`
- `0x140037d20`
- `0x140037df4`
- `0x140037edc`
- `0x14003817c`
- `0x140038228`
- `0x140038558`
- `0x140038798`
- `0x14003a930`
- `0x14003af90`
- `0x14003bac0`
- `0x14003c1b8`
- `0x14003c718`
- `0x14003d180`
- `0x14003d620`
- `0x14003db70`
- `0x140040350`
- `0x140040944`
- `0x140040b00`
- `0x140040c48`
- `0x140041b3c`
- `0x140042070`
- `0x14004229c`
- `0x140042688`
- `0x1400433b8`
- `0x1400434e4`
- `0x1400437e0`
- `0x140043a6c`
- `0x140043b1c`

## callees

- `0x140013b00`
- `0x140013c60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140013b3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140013b3c`
- `VssTrace!__imp_VssTraceMessage` at `0x140013c43`
- `VssTrace!__imp_VssTraceMessage` at `0x140013c43`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140013bef`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140013bef`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140013b78`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140013b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013bdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVssFunctionTracer::CVssFunctionTracer(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD TickCount; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // ebx
  __int64 i; // rbx
  void *v10; // rcx
  __int64 v12; // [rsp+80h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 8) = 0;
  if ( !a3 )
    a3 = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a1 + 40) = a3;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)a2;
  *(_QWORD *)(a1 + 24) = *(_QWORD *)(a2 + 16);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 36) = *(_DWORD *)(a2 + 28);
  TickCount = GetTickCount();
  *(_DWORD *)(a1 + 4) = -1;
  *(_DWORD *)(a1 + 52) = TickCount;
  *(_DWORD *)(a1 + 56) = *(_DWORD *)(a2 + 32);
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  v12 = 0;
  if ( (int)VssGetTracingContextPerThread(&v12) >= 0 && (int)VssSetTracingContextPerThread(a1) >= 0 )
    *(_QWORD *)(a1 + 96) = v12;
  v6 = *(_QWORD *)(a1 + 96);
  if ( v6 )
    v7 = *(_DWORD *)(v6 + 48) + 1;
  else
    v7 = 0;
  *(_DWORD *)(a1 + 48) = v7;
  v8 = 160;
  if ( *(_DWORD *)(a1 + 56) != 255 )
    v8 = *(_DWORD *)(a1 + 56);
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)a1, *(_DWORD *)(a1 + 36)) )
    VssTraceMessage(
      *(_QWORD *)(a1 + 16),
      *(_QWORD *)(a1 + 24),
      *(unsigned int *)(a1 + 32),
      *(unsigned int *)(a1 + 48),
      *(_DWORD *)(a1 + 36),
      *(_QWORD *)(a1 + 40),
      L"ENTER",
      v8,
      0);
  if ( *(_BYTE *)(a2 + 163) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v10 = *(void **)(a2 + 8 * i + 40);
      if ( v10 )
      {
        CoTaskMemFree(v10);
        *(_QWORD *)(a2 + 8 * i + 40) = 0;
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140013b00  push    rbx
0x140013b02  push    rbp
0x140013b03  push    rsi
0x140013b04  push    rdi
0x140013b05  sub     rsp, 58h
0x140013b09  xor     ebp, ebp
0x140013b0b  mov     rdi, rdx
0x140013b0e  mov     [rcx+8], ebp
0x140013b11  mov     rsi, rcx
0x140013b14  test    r8, r8
0x140013b17  jnz     short loc_140013B1D
0x140013b19  mov     r8, [rdx+8]
0x140013b1d  mov     [rcx+28h], r8
0x140013b21  mov     rax, [rdx]
0x140013b24  mov     [rcx+10h], rax
0x140013b28  mov     rax, [rdx+10h]
0x140013b2c  mov     [rcx+18h], rax
0x140013b30  mov     eax, [rdx+18h]
0x140013b33  mov     [rcx+20h], eax
0x140013b36  mov     eax, [rdx+1Ch]
0x140013b39  mov     [rcx+24h], eax
0x140013b3c  call    cs:__imp_GetTickCount
0x140013b42  mov     dword ptr [rsi+4], 0FFFFFFFFh
0x140013b49  lea     rcx, [rsp+78h+arg_0]
0x140013b51  mov     [rsi+34h], eax
0x140013b54  mov     eax, [rdi+20h]
0x140013b57  mov     [rsi+38h], eax
0x140013b5a  mov     [rsi], ebp
0x140013b5c  mov     [rsi+60h], rbp
0x140013b60  mov     [rsi+40h], rbp
0x140013b64  mov     [rsi+48h], rbp
0x140013b68  mov     [rsi+50h], rbp
0x140013b6c  mov     [rsi+58h], rbp
0x140013b70  mov     [rsp+78h+arg_0], rbp
0x140013b78  call    cs:__imp_VssGetTracingContextPerThread
0x140013b7e  test    eax, eax
0x140013b80  jns     short loc_140013BEC
0x140013b82  mov     rax, [rsi+60h]
0x140013b86  test    rax, rax
0x140013b89  jz      short loc_140013C0A
0x140013b8b  mov     eax, [rax+30h]
0x140013b8e  inc     eax
0x140013b90  mov     [rsi+30h], eax
0x140013b93  mov     ebx, 0A0h
0x140013b98  cmp     dword ptr [rsi+38h], 0FFh
0x140013b9f  mov     rcx, rsi; this
0x140013ba2  mov     edx, [rsi+24h]; unsigned int
0x140013ba5  cmovnz  ebx, [rsi+38h]
0x140013ba9  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140013bae  test    eax, eax
0x140013bb0  jnz     short loc_140013C0E
0x140013bb2  cmp     [rdi+0A3h], bpl
0x140013bb9  jz      short loc_140013BD3
0x140013bbb  mov     rbx, rbp
0x140013bbe  xchg    ax, ax
0x140013bc0  mov     rcx, [rdi+rbx*8+28h]; pv
0x140013bc5  test    rcx, rcx
0x140013bc8  jnz     short loc_140013BDF
0x140013bca  inc     rbx
0x140013bcd  cmp     rbx, 0Fh
0x140013bd1  jnz     short loc_140013BC0
0x140013bd3  mov     rax, rsi
0x140013bd6  add     rsp, 58h
0x140013bda  pop     rdi
0x140013bdb  pop     rsi
0x140013bdc  pop     rbp
0x140013bdd  pop     rbx
0x140013bde  retn
0x140013bdf  call    cs:__imp_CoTaskMemFree
0x140013be5  mov     [rdi+rbx*8+28h], rbp
0x140013bea  jmp     short loc_140013BCA
0x140013bec  mov     rcx, rsi
0x140013bef  call    cs:__imp_VssSetTracingContextPerThread
0x140013bf5  test    eax, eax
0x140013bf7  js      short loc_140013B82
0x140013bf9  mov     rax, [rsp+78h+arg_0]
0x140013c01  mov     [rsi+60h], rax
0x140013c05  jmp     loc_140013B82
0x140013c0a  mov     eax, ebp
0x140013c0c  jmp     short loc_140013B90
0x140013c0e  mov     r9d, [rsi+30h]
0x140013c12  lea     rax, aEnter; "ENTER"
0x140013c19  mov     r8d, [rsi+20h]
0x140013c1d  mov     rdx, [rsi+18h]
0x140013c21  mov     rcx, [rsi+10h]
0x140013c25  mov     [rsp+78h+var_38], rbp
0x140013c2a  mov     [rsp+78h+var_40], ebx
0x140013c2e  mov     [rsp+78h+var_48], rax
0x140013c33  mov     rax, [rsi+28h]
0x140013c37  mov     [rsp+78h+var_50], rax
0x140013c3c  mov     eax, [rsi+24h]
0x140013c3f  mov     [rsp+78h+var_58], eax
0x140013c43  call    cs:__imp_VssTraceMessage
0x140013c49  jmp     loc_140013BB2
```
