# InterfaceMgr::~InterfaceMgr(void)

- ea: `0x18000ff48`
- end: `0x18000ffbf`
- name: `??1InterfaceMgr@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(InterfaceMgr *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180014ab0`
- `0x180031e60`

## callees

- `0x18000bf4c`
- `0x18000ff48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ff87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ff87`

## pseudocode

```c
void __fastcall InterfaceMgr::~InterfaceMgr(InterfaceMgr *this)
{
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
}

```

## disassembly

```asm
0x18000ff48  mov     [rsp+arg_0], rbx
0x18000ff4d  push    rdi
0x18000ff4e  sub     rsp, 20h
0x18000ff52  mov     rbx, rcx
0x18000ff55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff5c  lea     rdi, WPP_GLOBAL_Control
0x18000ff63  cmp     rcx, rdi
0x18000ff66  jz      short loc_18000FF83
0x18000ff68  test    byte ptr [rcx+1Ch], 8
0x18000ff6c  jz      short loc_18000FF83
0x18000ff6e  mov     rcx, [rcx+10h]
0x18000ff72  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x18000ff79  mov     edx, 0Ch
0x18000ff7e  call    WPP_SF_
0x18000ff83  lea     rcx, [rbx+8]; lpCriticalSection
0x18000ff87  call    cs:__imp_DeleteCriticalSection
0x18000ff8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff94  cmp     rcx, rdi
0x18000ff97  jz      short loc_18000FFB4
0x18000ff99  test    byte ptr [rcx+1Ch], 8
0x18000ff9d  jz      short loc_18000FFB4
0x18000ff9f  mov     rcx, [rcx+10h]
0x18000ffa3  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x18000ffaa  mov     edx, 0Dh
0x18000ffaf  call    WPP_SF_
0x18000ffb4  mov     rbx, [rsp+28h+arg_0]
0x18000ffb9  add     rsp, 20h
0x18000ffbd  pop     rdi
0x18000ffbe  retn
```
