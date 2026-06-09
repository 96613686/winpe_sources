# CSsdpService::TimerFired(void)

- ea: `0x180013dac`
- end: `0x180013e60`
- name: `?TimerFired@CSsdpService@@QEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CSsdpService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180024a10`

## callees

- `0x180012760`
- `0x180013dac`
- `0x180013e70`
- `0x180014048`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013df1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013df1`

## pseudocode

```c
void __fastcall CSsdpService::TimerFired(const WCHAR **this)
{
  int MultiByteWithAlloc; // eax
  struct sockaddr *v3; // rdx
  bool v4; // zf
  int v5; // edx
  DWORD v6; // edx
  void *Block; // [rsp+30h] [rbp+8h] BYREF

  if ( ((_BYTE)this[33] & 2) == 0 && !*((_DWORD *)this + 24) )
  {
    Block = 0;
    MultiByteWithAlloc = CUString::HrGetMultiByteWithAlloc(this + 25, (char **)&Block);
    v4 = MultiByteWithAlloc == 0;
    if ( MultiByteWithAlloc >= 0 )
    {
      SendOnAllNetworks((char *)Block, v3);
      free(Block);
      v4 = (*((_DWORD *)this + 25))-- == 1;
      if ( v4 )
      {
        v5 = 500 * *((_DWORD *)this + 26);
        *((_DWORD *)this + 25) = 3;
        v6 = v5 - 12000;
      }
      else
      {
        v6 = 3000;
      }
      MultiByteWithAlloc = CTimerBase::HrSetTimerInFired((CTimerBase *)this, v6);
      v4 = MultiByteWithAlloc == 0;
    }
    if ( !v4 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids,
        (unsigned int)MultiByteWithAlloc);
  }
}

```

## disassembly

```asm
0x180013dac  push    rbx
0x180013dae  sub     rsp, 20h
0x180013db2  test    byte ptr [rcx+108h], 2
0x180013db9  mov     rbx, rcx
0x180013dbc  jnz     short loc_180013E1D
0x180013dbe  cmp     dword ptr [rcx+60h], 0
0x180013dc2  jnz     short loc_180013E1D
0x180013dc4  add     rcx, 0C8h; this
0x180013dcb  mov     [rsp+28h+Block], 0
0x180013dd4  lea     rdx, [rsp+28h+Block]; char **
0x180013dd9  call    ?HrGetMultiByteWithAlloc@CUString@@QEBAJPEAPEAD@Z; CUString::HrGetMultiByteWithAlloc(char * *)
0x180013dde  test    eax, eax
0x180013de0  js      short loc_180013E1B
0x180013de2  mov     rcx, [rsp+28h+Block]; char *
0x180013de7  call    ?SendOnAllNetworks@@YAXPEADPEAUsockaddr@@@Z; SendOnAllNetworks(char *,sockaddr *)
0x180013dec  mov     rcx, [rsp+28h+Block]; Block
0x180013df1  call    cs:__imp_free
0x180013df7  sub     dword ptr [rbx+64h], 1
0x180013dfb  mov     rcx, rbx; this
0x180013dfe  jnz     short loc_180013E23
0x180013e00  imul    edx, [rbx+68h], 1F4h
0x180013e07  mov     dword ptr [rbx+64h], 3
0x180013e0e  sub     edx, 2EE0h; DueTime
0x180013e14  call    ?HrSetTimerInFired@CTimerBase@@QEAAJK@Z; CTimerBase::HrSetTimerInFired(ulong)
0x180013e19  test    eax, eax
0x180013e1b  jnz     short loc_180013E2A
0x180013e1d  add     rsp, 20h
0x180013e21  pop     rbx
0x180013e22  retn
0x180013e23  mov     edx, 0BB8h
0x180013e28  jmp     short loc_180013E14
0x180013e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e31  lea     rdx, WPP_GLOBAL_Control
0x180013e38  cmp     rcx, rdx
0x180013e3b  jz      short loc_180013E1D
0x180013e3d  test    byte ptr [rcx+1Ch], 1
0x180013e41  jz      short loc_180013E1D
0x180013e43  mov     rcx, [rcx+10h]
0x180013e47  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180013e4e  mov     edx, 0Ah
0x180013e53  mov     r9d, eax
0x180013e56  add     rsp, 20h
0x180013e5a  pop     rbx
0x180013e5b  jmp     WPP_SF_d
```
