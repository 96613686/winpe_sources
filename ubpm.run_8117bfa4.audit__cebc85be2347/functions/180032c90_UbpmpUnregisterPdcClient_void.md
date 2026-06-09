# UbpmpUnregisterPdcClient(void)

- ea: `0x180032c90`
- end: `0x180032d36`
- name: `?UbpmpUnregisterPdcClient@@YAXXZ`
- size: `166`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180032acc`

## callees

- `0x180032c90`
- `0x1800351ec`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180032cd0`
- `ntdll!RtlNtStatusToDosError` at `0x180032cd0`
- `UMPDC!PdcActivationClientUnregister` at `0x180032d04`
- `UMPDC!PdcActivationClientUnregister` at `0x180032d04`
- `UMPDC!PdcTaskClientUnregister` at `0x180032d15`
- `UMPDC!PdcTaskClientUnregister` at `0x180032d15`

## pseudocode

```c
void UbpmpUnregisterPdcClient(void)
{
  NTSTATUS v0; // eax
  ULONG v1; // eax

  if ( !qword_18004FC38 )
    return;
  if ( dword_18004FC34 == 1 )
  {
    v0 = PdcTaskClientUnregister(qword_18004FC38);
LABEL_11:
    if ( v0 >= 0 )
    {
      qword_18004FC38 = 0;
      return;
    }
    goto LABEL_5;
  }
  if ( dword_18004FC34 == 2 )
  {
    v0 = PdcActivationClientUnregister(qword_18004FC38);
    goto LABEL_11;
  }
  v0 = -1073741637;
LABEL_5:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v1 = RtlNtStatusToDosError(v0);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, v1);
  }
}

```

## disassembly

```asm
0x180032c90  sub     rsp, 28h
0x180032c94  mov     rdx, cs:qword_18004FC38
0x180032c9b  test    rdx, rdx
0x180032c9e  jz      short loc_180032CFB
0x180032ca0  mov     ecx, cs:dword_18004FC34
0x180032ca6  sub     ecx, 1
0x180032ca9  jz      short loc_180032D12
0x180032cab  cmp     ecx, 1
0x180032cae  jz      short loc_180032D01
0x180032cb0  mov     eax, 0C00000BBh
0x180032cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180032cbc  lea     rdx, WPP_GLOBAL_Control
0x180032cc3  cmp     rcx, rdx
0x180032cc6  jz      short loc_180032CFB
0x180032cc8  test    byte ptr [rcx+1Ch], 1
0x180032ccc  jz      short loc_180032CFB
0x180032cce  mov     ecx, eax; Status
0x180032cd0  call    cs:__imp_RtlNtStatusToDosError
0x180032cd7  nop     dword ptr [rax+rax+00h]
0x180032cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ce3  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x180032cea  mov     edx, 14h
0x180032cef  mov     r9d, eax
0x180032cf2  mov     rcx, [rcx+10h]
0x180032cf6  call    WPP_SF_d
0x180032cfb  add     rsp, 28h
0x180032cff  retn
0x180032d01  mov     rcx, rdx
0x180032d04  call    cs:__imp_PdcActivationClientUnregister
0x180032d0b  nop     dword ptr [rax+rax+00h]
0x180032d10  jmp     short loc_180032D21
0x180032d12  mov     rcx, rdx
0x180032d15  call    cs:__imp_PdcTaskClientUnregister
0x180032d1c  nop     dword ptr [rax+rax+00h]
0x180032d21  test    eax, eax
0x180032d23  js      short loc_180032CB5
0x180032d25  mov     cs:qword_18004FC38, 0
0x180032d30  add     rsp, 28h
0x180032d34  retn
```
