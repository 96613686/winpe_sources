# CSsdpService::RestartAnnouncing(int)

- ea: `0x180031fbc`
- end: `0x180032060`
- name: `?RestartAnnouncing@CSsdpService@@QEAAXH@Z`
- size: `164`
- prototype: `void __fastcall(PVOID Parameter, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000fec0`
- `0x1800201a0`

## callees

- `0x180008800`
- `0x180031fbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18003200d`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18003200d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031fda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031fda`

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
0x180031fbc  mov     [rsp+arg_0], rbx
0x180031fc1  mov     [rsp+arg_8], rsi
0x180031fc6  push    rdi
0x180031fc7  sub     rsp, 20h
0x180031fcb  lea     rdi, [rcx+0E0h]
0x180031fd2  mov     rbx, rcx
0x180031fd5  mov     rcx, rdi; lpCriticalSection
0x180031fd8  mov     esi, edx
0x180031fda  call    cs:__imp_EnterCriticalSection
0x180031fe1  nop     dword ptr [rax+rax+00h]
0x180031fe6  test    byte ptr [rbx+108h], 2
0x180031fed  jnz     short loc_180032042
0x180031fef  cmp     dword ptr [rbx+60h], 0
0x180031ff3  jz      short loc_180031FFB
0x180031ff5  test    esi, esi
0x180031ff7  jnz     short loc_180031FFF
0x180031ff9  jmp     short loc_180032042
0x180031ffb  test    esi, esi
0x180031ffd  jz      short loc_180032006
0x180031fff  mov     dword ptr [rbx+60h], 0
0x180032006  mov     dword ptr [rbx+64h], 3
0x18003200d  call    cs:__imp_rand
0x180032014  nop     dword ptr [rax+rax+00h]
0x180032019  mov     r8d, eax
0x18003201c  mov     rcx, rbx; Parameter
0x18003201f  mov     eax, 57619F1h
0x180032024  imul    r8d
0x180032027  sar     edx, 6
0x18003202a  mov     eax, edx
0x18003202c  shr     eax, 1Fh
0x18003202f  add     edx, eax
0x180032031  imul    eax, edx, 0BB8h
0x180032037  sub     r8d, eax
0x18003203a  mov     edx, r8d; DueTime
0x18003203d  call    ?HrResetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrResetTimer(ulong)
0x180032042  mov     rcx, rdi
0x180032045  mov     rbx, [rsp+28h+arg_0]
0x18003204a  mov     rsi, [rsp+28h+arg_8]
0x18003204f  add     rsp, 20h
0x180032053  pop     rdi
0x180032054  jmp     cs:__imp_LeaveCriticalSection
```
