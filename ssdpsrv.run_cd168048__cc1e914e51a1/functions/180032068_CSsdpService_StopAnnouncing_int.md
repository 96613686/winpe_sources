# CSsdpService::StopAnnouncing(int)

- ea: `0x180032068`
- end: `0x18003211e`
- name: `?StopAnnouncing@CSsdpService@@QEAAXH@Z`
- size: `182`
- prototype: `void __fastcall(CSsdpService *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001cdb4`

## callees

- `0x180014f80`
- `0x1800268e0`
- `0x18003106c`
- `0x180032068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032112`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003207f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003207f`

## pseudocode

```c
void __fastcall CSsdpService::StopAnnouncing(CSsdpService *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  bool v3; // zf
  char *v4; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  if ( !*((_DWORD *)this + 24) )
  {
    v3 = (*((_BYTE *)this + 264) & 2) == 0;
    *((_DWORD *)this + 24) = 1;
    if ( v3 )
    {
      v4 = 0;
      if ( (int)CUString::HrGetMultiByteWithAlloc((CSsdpService *)((char *)this + 208), &v4) >= 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids,
            *((_QWORD *)this + 35));
        CSsdpByebye::Create(v4, (CSsdpService *)((char *)this + 280));
      }
    }
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180032068  mov     [rsp+arg_8], rbx
0x18003206d  push    rdi
0x18003206e  sub     rsp, 20h
0x180032072  lea     rdi, [rcx+0E0h]
0x180032079  mov     rbx, rcx
0x18003207c  mov     rcx, rdi; lpCriticalSection
0x18003207f  call    cs:__imp_EnterCriticalSection
0x180032086  nop     dword ptr [rax+rax+00h]
0x18003208b  cmp     dword ptr [rbx+60h], 0
0x18003208f  jnz     short loc_180032105
0x180032091  test    byte ptr [rbx+108h], 2
0x180032098  mov     dword ptr [rbx+60h], 1
0x18003209f  jnz     short loc_180032105
0x1800320a1  lea     rcx, [rbx+0D0h]; this
0x1800320a8  mov     [rsp+28h+arg_0], 0
0x1800320b1  lea     rdx, [rsp+28h+arg_0]; char **
0x1800320b6  call    ?HrGetMultiByteWithAlloc@CUString@@QEBAJPEAPEAD@Z; CUString::HrGetMultiByteWithAlloc(char * *)
0x1800320bb  test    eax, eax
0x1800320bd  js      short loc_180032105
0x1800320bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320c6  lea     rax, WPP_GLOBAL_Control
0x1800320cd  cmp     rcx, rax
0x1800320d0  jz      short loc_1800320F4
0x1800320d2  test    byte ptr [rcx+1Ch], 8
0x1800320d6  jz      short loc_1800320F4
0x1800320d8  mov     r9, [rbx+118h]
0x1800320df  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x1800320e6  mov     rcx, [rcx+10h]
0x1800320ea  mov     edx, 15h
0x1800320ef  call    WPP_SF_S
0x1800320f4  mov     rcx, [rsp+28h+arg_0]; char *
0x1800320f9  lea     rdx, [rbx+118h]; struct CUString *
0x180032100  call    ?Create@CSsdpByebye@@SAJPEADAEAVCUString@@@Z; CSsdpByebye::Create(char *,CUString &)
0x180032105  mov     rcx, rdi
0x180032108  mov     rbx, [rsp+28h+arg_8]
0x18003210d  add     rsp, 20h
0x180032111  pop     rdi
0x180032112  jmp     cs:__imp_LeaveCriticalSection
```
