# UbpmpUnregisterPdcClient(void)

- ea: `0x18003099c`
- end: `0x180030a2e`
- name: `?UbpmpUnregisterPdcClient@@YAXXZ`
- size: `146`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800307f0`

## callees

- `0x18003099c`
- `0x180032e38`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800309dc`
- `ntdll!RtlNtStatusToDosError` at `0x1800309dc`
- `UMPDC!PdcActivationClientUnregister` at `0x180030a09`
- `UMPDC!PdcActivationClientUnregister` at `0x180030a09`
- `UMPDC!PdcTaskClientUnregister` at `0x180030a14`
- `UMPDC!PdcTaskClientUnregister` at `0x180030a14`

## pseudocode

```c
void UbpmpUnregisterPdcClient(void)
{
  NTSTATUS v0; // eax
  ULONG v1; // eax

  if ( !qword_18004CB38 )
    return;
  if ( dword_18004CB34 == 1 )
  {
    v0 = PdcTaskClientUnregister(qword_18004CB38);
LABEL_11:
    if ( v0 >= 0 )
    {
      qword_18004CB38 = 0;
      return;
    }
    goto LABEL_5;
  }
  if ( dword_18004CB34 == 2 )
  {
    v0 = PdcActivationClientUnregister(qword_18004CB38);
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
0x18003099c  sub     rsp, 28h
0x1800309a0  mov     rdx, cs:qword_18004CB38
0x1800309a7  test    rdx, rdx
0x1800309aa  jz      short loc_180030A01
0x1800309ac  mov     ecx, cs:dword_18004CB34
0x1800309b2  sub     ecx, 1
0x1800309b5  jz      short loc_180030A11
0x1800309b7  cmp     ecx, 1
0x1800309ba  jz      short loc_180030A06
0x1800309bc  mov     eax, 0C00000BBh
0x1800309c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309c8  lea     rdx, WPP_GLOBAL_Control
0x1800309cf  cmp     rcx, rdx
0x1800309d2  jz      short loc_180030A01
0x1800309d4  test    byte ptr [rcx+1Ch], 1
0x1800309d8  jz      short loc_180030A01
0x1800309da  mov     ecx, eax; Status
0x1800309dc  call    cs:__imp_RtlNtStatusToDosError
0x1800309e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309e9  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x1800309f0  mov     edx, 14h
0x1800309f5  mov     r9d, eax
0x1800309f8  mov     rcx, [rcx+10h]
0x1800309fc  call    WPP_SF_d
0x180030a01  add     rsp, 28h
0x180030a05  retn
0x180030a06  mov     rcx, rdx
0x180030a09  call    cs:__imp_PdcActivationClientUnregister
0x180030a0f  jmp     short loc_180030A1A
0x180030a11  mov     rcx, rdx
0x180030a14  call    cs:__imp_PdcTaskClientUnregister
0x180030a1a  test    eax, eax
0x180030a1c  js      short loc_1800309C1
0x180030a1e  mov     cs:qword_18004CB38, 0
0x180030a29  add     rsp, 28h
0x180030a2d  retn
```
