# CSsdpService::TimerFired(void)

- ea: `0x180014eb0`
- end: `0x180014f6b`
- name: `?TimerFired@CSsdpService@@QEAAXXZ`
- size: `187`
- prototype: `void __fastcall(CSsdpService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180026540`

## callees

- `0x180014eb0`
- `0x180014f80`
- `0x1800152c0`
- `0x180016570`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014ef5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014ef5`

## pseudocode

```c
void __fastcall CSsdpService::TimerFired(CSsdpService *this)
{
  int MultiByteWithAlloc; // eax
  struct sockaddr *v3; // rdx
  bool v4; // zf
  int v5; // edx
  DWORD v6; // edx
  void *Block; // [rsp+30h] [rbp+8h] BYREF

  if ( (*((_BYTE *)this + 264) & 2) == 0 && !*((_DWORD *)this + 24) )
  {
    Block = 0;
    MultiByteWithAlloc = CUString::HrGetMultiByteWithAlloc((CSsdpService *)((char *)this + 200), (char **)&Block);
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
      MultiByteWithAlloc = CTimerBase::HrSetTimerInFired(this, v6);
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
0x180014eb0  push    rbx
0x180014eb2  sub     rsp, 20h
0x180014eb6  test    byte ptr [rcx+108h], 2
0x180014ebd  mov     rbx, rcx
0x180014ec0  jnz     short loc_180014F27
0x180014ec2  cmp     dword ptr [rcx+60h], 0
0x180014ec6  jnz     short loc_180014F27
0x180014ec8  add     rcx, 0C8h; this
0x180014ecf  mov     [rsp+28h+Block], 0
0x180014ed8  lea     rdx, [rsp+28h+Block]; char **
0x180014edd  call    ?HrGetMultiByteWithAlloc@CUString@@QEBAJPEAPEAD@Z; CUString::HrGetMultiByteWithAlloc(char * *)
0x180014ee2  test    eax, eax
0x180014ee4  js      short loc_180014F25
0x180014ee6  mov     rcx, [rsp+28h+Block]; char *
0x180014eeb  call    ?SendOnAllNetworks@@YAXPEADPEAUsockaddr@@@Z; SendOnAllNetworks(char *,sockaddr *)
0x180014ef0  mov     rcx, [rsp+28h+Block]; Block
0x180014ef5  call    cs:__imp_free
0x180014efc  nop     dword ptr [rax+rax+00h]
0x180014f01  sub     dword ptr [rbx+64h], 1
0x180014f05  mov     rcx, rbx; this
0x180014f08  jnz     short loc_180014F2E
0x180014f0a  imul    edx, [rbx+68h], 1F4h
0x180014f11  mov     dword ptr [rbx+64h], 3
0x180014f18  sub     edx, 2EE0h; DueTime
0x180014f1e  call    ?HrSetTimerInFired@CTimerBase@@QEAAJK@Z; CTimerBase::HrSetTimerInFired(ulong)
0x180014f23  test    eax, eax
0x180014f25  jnz     short loc_180014F35
0x180014f27  add     rsp, 20h
0x180014f2b  pop     rbx
0x180014f2c  retn
0x180014f2e  mov     edx, 0BB8h
0x180014f33  jmp     short loc_180014F1E
0x180014f35  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f3c  lea     rdx, WPP_GLOBAL_Control
0x180014f43  cmp     rcx, rdx
0x180014f46  jz      short loc_180014F27
0x180014f48  test    byte ptr [rcx+1Ch], 1
0x180014f4c  jz      short loc_180014F27
0x180014f4e  mov     rcx, [rcx+10h]
0x180014f52  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180014f59  mov     edx, 0Ah
0x180014f5e  mov     r9d, eax
0x180014f61  add     rsp, 20h
0x180014f65  pop     rbx
0x180014f66  jmp     WPP_SF_d
```
