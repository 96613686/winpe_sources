# GmoMigrationMemoryWalkerWorker::RunInitialize(void)

- ea: `0x140241200`
- end: `0x1402412dd`
- name: `?RunInitialize@GmoMigrationMemoryWalkerWorker@@MEAAXXZ`
- size: `221`
- prototype: `void __fastcall(GmoMigrationMemoryWalkerWorker *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140042260`
- `0x14005497c`
- `0x140111090`
- `0x140132960`
- `0x140241200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14024126f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14024126f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140241235`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140241235`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x14024124c`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x14024124c`

## pseudocode

```c
void __fastcall GmoMigrationMemoryWalkerWorker::RunInitialize(GmoMigrationMemoryWalkerWorker *this)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  GROUP_AFFINITY GroupAffinity; // [rsp+30h] [rbp-28h] BYREF

  GroupAffinity = *(GROUP_AFFINITY *)(*((_QWORD *)this + 35) + 160LL);
  if ( GroupAffinity.Mask )
  {
    CurrentThread = GetCurrentThread();
    if ( !SetThreadGroupAffinity(CurrentThread, &GroupAffinity, 0) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
      {
        LastError = GetLastError();
        VmlDebugTraceWithError(16866, &off_1402DB658, LastError);
      }
    }
  }
  else if ( (unsigned int)VmlIsDebugTraceEnabled(33250) )
  {
    VmlDebugTraceEx(33250, &off_1402DB640);
  }
}

```

## disassembly

```asm
0x140241200  push    rbx
0x140241202  sub     rsp, 50h
0x140241206  mov     rax, cs:__security_cookie
0x14024120d  xor     rax, rsp
0x140241210  mov     [rsp+58h+var_18], rax
0x140241215  mov     rax, [rcx+118h]
0x14024121c  mov     rbx, rcx
0x14024121f  movups  xmm0, xmmword ptr [rax+0A0h]
0x140241226  movq    rax, xmm0
0x14024122b  movups  xmmword ptr [rsp+58h+GroupAffinity.Mask], xmm0
0x140241230  test    rax, rax
0x140241233  jz      short loc_14024129E
0x140241235  call    cs:__imp_GetCurrentThread
0x14024123c  nop     dword ptr [rax+rax+00h]
0x140241241  xor     r8d, r8d; PreviousGroupAffinity
0x140241244  lea     rdx, [rsp+58h+GroupAffinity]; GroupAffinity
0x140241249  mov     rcx, rax; hThread
0x14024124c  call    cs:__imp_SetThreadGroupAffinity
0x140241253  nop     dword ptr [rax+rax+00h]
0x140241258  test    eax, eax
0x14024125a  jnz     short loc_1402412C9
0x14024125c  mov     ecx, 41E2h
0x140241261  call    VmlIsDebugTraceEnabled
0x140241266  test    eax, eax
0x140241268  jz      short loc_1402412C9
0x14024126a  movzx   ebx, [rsp+58h+GroupAffinity.Group]
0x14024126f  call    cs:__imp_GetLastError
0x140241276  nop     dword ptr [rax+rax+00h]
0x14024127b  mov     r9d, ebx
0x14024127e  lea     rdx, off_1402DB658; "Failed to set thread affinity group:0x'"...
0x140241285  mov     r8d, eax
0x140241288  mov     ecx, 41E2h
0x14024128d  mov     rax, [rsp+58h+GroupAffinity.Mask]
0x140241292  mov     [rsp+58h+var_38], rax
0x140241297  call    VmlDebugTraceWithError
0x14024129c  jmp     short loc_1402412C9
0x14024129e  mov     ecx, 81E2h
0x1402412a3  call    VmlIsDebugTraceEnabled
0x1402412a8  test    eax, eax
0x1402412aa  jz      short loc_1402412C9
0x1402412ac  mov     rax, [rbx+118h]
0x1402412b3  lea     rdx, off_1402DB640; "Found CPU less NUMA node '%u'."
0x1402412ba  mov     ecx, 81E2h
0x1402412bf  movzx   r8d, byte ptr [rax+78h]
0x1402412c4  call    VmlDebugTraceEx
0x1402412c9  mov     rcx, [rsp+58h+var_18]
0x1402412ce  xor     rcx, rsp; StackCookie
0x1402412d1  call    __security_check_cookie
0x1402412d6  add     rsp, 50h
0x1402412da  pop     rbx
0x1402412db  retn
```
