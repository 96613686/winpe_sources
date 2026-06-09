# CSsdpService::HrCleanup(int)

- ea: `0x18001587c`
- end: `0x180015974`
- name: `?HrCleanup@CSsdpService@@QEAAJH@Z`
- size: `248`
- prototype: `__int64 __fastcall(CSsdpService *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002021c`

## callees

- `0x180013e70`
- `0x180015720`
- `0x18001587c`
- `0x180024d98`
- `0x1800255a8`
- `0x18002ee3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015959`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015959`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001589d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001589d`

## pseudocode

```c
__int64 __fastcall CSsdpService::HrCleanup(CSsdpService *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int MultiByteWithAlloc; // ebx
  char *v7; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  MultiByteWithAlloc = CTimerBase::HrDelete(this, (void *)0xFFFFFFFFFFFFFFFFLL);
  if ( MultiByteWithAlloc >= 0 )
  {
    if ( a2 )
    {
      if ( (*((_BYTE *)this + 264) & 2) == 0 )
      {
        v7 = 0;
        MultiByteWithAlloc = CUString::HrGetMultiByteWithAlloc((CSsdpService *)((char *)this + 208), &v7);
        if ( MultiByteWithAlloc >= 0 )
        {
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids,
              *((_QWORD *)this + 35));
          CSsdpByebye::Create(v7, (CSsdpService *)((char *)this + 280));
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
0x18001587c  mov     [rsp+arg_8], rbx
0x180015881  mov     [rsp+arg_10], rbp
0x180015886  push    rsi
0x180015887  push    rdi
0x180015888  push    r14
0x18001588a  sub     rsp, 20h
0x18001588e  lea     rbp, [rcx+0E0h]
0x180015895  mov     rdi, rcx
0x180015898  mov     rcx, rbp; lpCriticalSection
0x18001589b  mov     esi, edx
0x18001589d  call    cs:__imp_EnterCriticalSection
0x1800158a3  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x1800158a7  mov     rcx, rdi; this
0x1800158aa  call    ?HrDelete@CTimerBase@@QEAAJPEAX@Z; CTimerBase::HrDelete(void *)
0x1800158af  lea     r14, WPP_GLOBAL_Control
0x1800158b6  mov     ebx, eax
0x1800158b8  test    eax, eax
0x1800158ba  js      short loc_180015928
0x1800158bc  test    esi, esi
0x1800158be  jz      short loc_180015928
0x1800158c0  test    byte ptr [rdi+108h], 2
0x1800158c7  jnz     short loc_180015928
0x1800158c9  lea     rcx, [rdi+0D0h]; this
0x1800158d0  mov     [rsp+38h+arg_0], 0
0x1800158d9  lea     rdx, [rsp+38h+arg_0]; char **
0x1800158de  call    ?HrGetMultiByteWithAlloc@CUString@@QEBAJPEAPEAD@Z; CUString::HrGetMultiByteWithAlloc(char * *)
0x1800158e3  mov     ebx, eax
0x1800158e5  test    eax, eax
0x1800158e7  js      short loc_180015928
0x1800158e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158f0  cmp     rcx, r14
0x1800158f3  jz      short loc_180015917
0x1800158f5  test    byte ptr [rcx+1Ch], 8
0x1800158f9  jz      short loc_180015917
0x1800158fb  mov     r9, [rdi+118h]
0x180015902  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180015909  mov     rcx, [rcx+10h]
0x18001590d  mov     edx, 19h
0x180015912  call    WPP_SF_S
0x180015917  mov     rcx, [rsp+38h+arg_0]; char *
0x18001591c  lea     rdx, [rdi+118h]; struct CUString *
0x180015923  call    ?Create@CSsdpByebye@@SAJPEADAEAVCUString@@@Z; CSsdpByebye::Create(char *,CUString &)
0x180015928  test    ebx, ebx
0x18001592a  jz      short loc_180015956
0x18001592c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015933  cmp     rcx, r14
0x180015936  jz      short loc_180015956
0x180015938  test    byte ptr [rcx+1Ch], 1
0x18001593c  jz      short loc_180015956
0x18001593e  mov     rcx, [rcx+10h]
0x180015942  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180015949  mov     edx, 1Ah
0x18001594e  mov     r9d, ebx
0x180015951  call    WPP_SF_d
0x180015956  mov     rcx, rbp; lpCriticalSection
0x180015959  call    cs:__imp_LeaveCriticalSection
0x18001595f  mov     rbp, [rsp+38h+arg_10]
0x180015964  mov     eax, ebx
0x180015966  mov     rbx, [rsp+38h+arg_8]
0x18001596b  add     rsp, 20h
0x18001596f  pop     r14
0x180015971  pop     rdi
0x180015972  pop     rsi
0x180015973  retn
```
