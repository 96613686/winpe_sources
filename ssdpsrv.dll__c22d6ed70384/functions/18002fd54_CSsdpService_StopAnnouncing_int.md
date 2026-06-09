# CSsdpService::StopAnnouncing(int)

- ea: `0x18002fd54`
- end: `0x18002fdff`
- name: `?StopAnnouncing@CSsdpService@@QEAAXH@Z`
- size: `171`
- prototype: `void __fastcall(CSsdpService *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001ba64`

## callees

- `0x180013e70`
- `0x180024d98`
- `0x18002ee3c`
- `0x18002fd54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fdf8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fd6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fd6b`

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
      if ( (int)CUString::HrGetMultiByteWithAlloc((const WCHAR **)this + 26, &v4) >= 0 )
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
0x18002fd54  mov     [rsp+arg_8], rbx
0x18002fd59  push    rdi
0x18002fd5a  sub     rsp, 20h
0x18002fd5e  lea     rdi, [rcx+0E0h]
0x18002fd65  mov     rbx, rcx
0x18002fd68  mov     rcx, rdi; lpCriticalSection
0x18002fd6b  call    cs:__imp_EnterCriticalSection
0x18002fd71  cmp     dword ptr [rbx+60h], 0
0x18002fd75  jnz     short loc_18002FDEB
0x18002fd77  test    byte ptr [rbx+108h], 2
0x18002fd7e  mov     dword ptr [rbx+60h], 1
0x18002fd85  jnz     short loc_18002FDEB
0x18002fd87  lea     rcx, [rbx+0D0h]; this
0x18002fd8e  mov     [rsp+28h+arg_0], 0
0x18002fd97  lea     rdx, [rsp+28h+arg_0]; char **
0x18002fd9c  call    ?HrGetMultiByteWithAlloc@CUString@@QEBAJPEAPEAD@Z; CUString::HrGetMultiByteWithAlloc(char * *)
0x18002fda1  test    eax, eax
0x18002fda3  js      short loc_18002FDEB
0x18002fda5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdac  lea     rax, WPP_GLOBAL_Control
0x18002fdb3  cmp     rcx, rax
0x18002fdb6  jz      short loc_18002FDDA
0x18002fdb8  test    byte ptr [rcx+1Ch], 8
0x18002fdbc  jz      short loc_18002FDDA
0x18002fdbe  mov     r9, [rbx+118h]
0x18002fdc5  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x18002fdcc  mov     rcx, [rcx+10h]
0x18002fdd0  mov     edx, 15h
0x18002fdd5  call    WPP_SF_S
0x18002fdda  mov     rcx, [rsp+28h+arg_0]; char *
0x18002fddf  lea     rdx, [rbx+118h]; struct CUString *
0x18002fde6  call    ?Create@CSsdpByebye@@SAJPEADAEAVCUString@@@Z; CSsdpByebye::Create(char *,CUString &)
0x18002fdeb  mov     rcx, rdi
0x18002fdee  mov     rbx, [rsp+28h+arg_8]
0x18002fdf3  add     rsp, 20h
0x18002fdf7  pop     rdi
0x18002fdf8  jmp     cs:__imp_LeaveCriticalSection
```
