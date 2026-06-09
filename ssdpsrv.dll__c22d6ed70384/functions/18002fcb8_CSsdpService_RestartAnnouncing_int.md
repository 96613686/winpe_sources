# CSsdpService::RestartAnnouncing(int)

- ea: `0x18002fcb8`
- end: `0x18002fd4b`
- name: `?RestartAnnouncing@CSsdpService@@QEAAXH@Z`
- size: `147`
- prototype: `void __fastcall(char *Parameter, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000ea40`
- `0x18001ec10`

## callees

- `0x180007360`
- `0x18002fcb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18002fd03`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18002fd03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fcd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fcd6`

## pseudocode

```c
void __fastcall CSsdpService::RestartAnnouncing(char *Parameter, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v5; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 224));
  if ( (Parameter[264] & 2) == 0 )
  {
    if ( *((_DWORD *)Parameter + 24) )
    {
      if ( !a2 )
        goto LABEL_8;
    }
    else if ( !a2 )
    {
LABEL_7:
      *((_DWORD *)Parameter + 25) = 3;
      v5 = rand();
      CTimerBase::HrResetTimer(Parameter, v5 % 3000);
      goto LABEL_8;
    }
    *((_DWORD *)Parameter + 24) = 0;
    goto LABEL_7;
  }
LABEL_8:
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18002fcb8  mov     [rsp+arg_0], rbx
0x18002fcbd  mov     [rsp+arg_8], rsi
0x18002fcc2  push    rdi
0x18002fcc3  sub     rsp, 20h
0x18002fcc7  lea     rdi, [rcx+0E0h]
0x18002fcce  mov     rbx, rcx
0x18002fcd1  mov     rcx, rdi; lpCriticalSection
0x18002fcd4  mov     esi, edx
0x18002fcd6  call    cs:__imp_EnterCriticalSection
0x18002fcdc  test    byte ptr [rbx+108h], 2
0x18002fce3  jnz     short loc_18002FD32
0x18002fce5  cmp     dword ptr [rbx+60h], 0
0x18002fce9  jz      short loc_18002FCF1
0x18002fceb  test    esi, esi
0x18002fced  jnz     short loc_18002FCF5
0x18002fcef  jmp     short loc_18002FD32
0x18002fcf1  test    esi, esi
0x18002fcf3  jz      short loc_18002FCFC
0x18002fcf5  mov     dword ptr [rbx+60h], 0
0x18002fcfc  mov     dword ptr [rbx+64h], 3
0x18002fd03  call    cs:__imp_rand
0x18002fd09  mov     r8d, eax
0x18002fd0c  mov     rcx, rbx; Parameter
0x18002fd0f  mov     eax, 57619F1h
0x18002fd14  imul    r8d
0x18002fd17  sar     edx, 6
0x18002fd1a  mov     eax, edx
0x18002fd1c  shr     eax, 1Fh
0x18002fd1f  add     edx, eax
0x18002fd21  imul    eax, edx, 0BB8h
0x18002fd27  sub     r8d, eax
0x18002fd2a  mov     edx, r8d; DueTime
0x18002fd2d  call    ?HrResetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrResetTimer(ulong)
0x18002fd32  mov     rcx, rdi
0x18002fd35  mov     rbx, [rsp+28h+arg_0]
0x18002fd3a  mov     rsi, [rsp+28h+arg_8]
0x18002fd3f  add     rsp, 20h
0x18002fd43  pop     rdi
0x18002fd44  jmp     cs:__imp_LeaveCriticalSection
```
