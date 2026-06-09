# CSsdpService::HrCleanup(int)

- ea: `0x180017ec0`
- end: `0x180017fc5`
- name: `?HrCleanup@CSsdpService@@QEAAJH@Z`
- size: `261`
- prototype: `__int64 __fastcall(CSsdpService *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800218ac`

## callees

- `0x180014f80`
- `0x180017d28`
- `0x180017ec0`
- `0x1800268e0`
- `0x1800271fc`
- `0x18003106c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017fa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017fa3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ee1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ee1`

## pseudocode

```c
__int64 __fastcall CSsdpService::HrCleanup(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int MultiByteWithAlloc; // ebx
  char *v7; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((struct _RTL_CRITICAL_SECTION *)((char *)this + 224));
  MultiByteWithAlloc = CTimerBase::HrDelete(this, (char *)0xFFFFFFFFFFFFFFFFLL);
  if ( MultiByteWithAlloc >= 0 )
  {
    if ( a2 )
    {
      if ( ((__int64)this[6].LockSemaphore & 2) == 0 )
      {
        v7 = 0;
        MultiByteWithAlloc = CUString::HrGetMultiByteWithAlloc((CUString *)&this[5].LockCount, &v7);
        if ( MultiByteWithAlloc >= 0 )
        {
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids,
              this[7].DebugInfo);
          CSsdpByebye::Create(v7, (struct CUString *)&this[7]);
        }
      }
    }
  }
  if ( MultiByteWithAlloc && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids,
      (unsigned int)MultiByteWithAlloc);
  LeaveCriticalSection(v2);
  return (unsigned int)MultiByteWithAlloc;
}

```

## disassembly

```asm
0x180017ec0  mov     [rsp+arg_8], rbx
0x180017ec5  mov     [rsp+arg_10], rbp
0x180017eca  push    rsi
0x180017ecb  push    rdi
0x180017ecc  push    r14
0x180017ece  sub     rsp, 20h
0x180017ed2  lea     rbp, [rcx+0E0h]
0x180017ed9  mov     rdi, rcx
0x180017edc  mov     rcx, rbp; lpCriticalSection
0x180017edf  mov     esi, edx
0x180017ee1  call    cs:__imp_EnterCriticalSection
0x180017ee8  nop     dword ptr [rax+rax+00h]
0x180017eed  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x180017ef1  mov     rcx, rdi; this
0x180017ef4  call    ?HrDelete@CTimerBase@@QEAAJPEAX@Z; CTimerBase::HrDelete(void *)
0x180017ef9  lea     r14, WPP_GLOBAL_Control
0x180017f00  mov     ebx, eax
0x180017f02  test    eax, eax
0x180017f04  js      short loc_180017F72
0x180017f06  test    esi, esi
0x180017f08  jz      short loc_180017F72
0x180017f0a  test    byte ptr [rdi+108h], 2
0x180017f11  jnz     short loc_180017F72
0x180017f13  lea     rcx, [rdi+0D0h]; this
0x180017f1a  mov     [rsp+38h+arg_0], 0
0x180017f23  lea     rdx, [rsp+38h+arg_0]; char **
0x180017f28  call    ?HrGetMultiByteWithAlloc@CUString@@QEBAJPEAPEAD@Z; CUString::HrGetMultiByteWithAlloc(char * *)
0x180017f2d  mov     ebx, eax
0x180017f2f  test    eax, eax
0x180017f31  js      short loc_180017F72
0x180017f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f3a  cmp     rcx, r14
0x180017f3d  jz      short loc_180017F61
0x180017f3f  test    byte ptr [rcx+1Ch], 8
0x180017f43  jz      short loc_180017F61
0x180017f45  mov     r9, [rdi+118h]
0x180017f4c  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180017f53  mov     rcx, [rcx+10h]
0x180017f57  mov     edx, 19h
0x180017f5c  call    WPP_SF_S
0x180017f61  mov     rcx, [rsp+38h+arg_0]; char *
0x180017f66  lea     rdx, [rdi+118h]; struct CUString *
0x180017f6d  call    ?Create@CSsdpByebye@@SAJPEADAEAVCUString@@@Z; CSsdpByebye::Create(char *,CUString &)
0x180017f72  test    ebx, ebx
0x180017f74  jz      short loc_180017FA0
0x180017f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f7d  cmp     rcx, r14
0x180017f80  jz      short loc_180017FA0
0x180017f82  test    byte ptr [rcx+1Ch], 1
0x180017f86  jz      short loc_180017FA0
0x180017f88  mov     rcx, [rcx+10h]
0x180017f8c  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180017f93  mov     edx, 1Ah
0x180017f98  mov     r9d, ebx
0x180017f9b  call    WPP_SF_d
0x180017fa0  mov     rcx, rbp; lpCriticalSection
0x180017fa3  call    cs:__imp_LeaveCriticalSection
0x180017faa  nop     dword ptr [rax+rax+00h]
0x180017faf  mov     rbp, [rsp+38h+arg_10]
0x180017fb4  mov     eax, ebx
0x180017fb6  mov     rbx, [rsp+38h+arg_8]
0x180017fbb  add     rsp, 20h
0x180017fbf  pop     r14
0x180017fc1  pop     rdi
0x180017fc2  pop     rsi
0x180017fc3  retn
```
