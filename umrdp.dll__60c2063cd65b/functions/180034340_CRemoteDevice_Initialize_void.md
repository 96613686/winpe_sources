# CRemoteDevice::Initialize(void)

- ea: `0x180034340`
- end: `0x1800343f4`
- name: `?Initialize@CRemoteDevice@@UEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(CRemoteDevice *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180033878`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x180034340`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180034369`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180034369`

## string_xrefs

- `0x180034399`: `CoCreateGuid FAILED`

## pseudocode

```c
__int64 __fastcall CRemoteDevice::Initialize(CRemoteDevice *this)
{
  HRESULT v2; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  GUID pguid; // [rsp+30h] [rbp-28h] BYREF

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 >= 0 )
  {
    *(GUID *)((char *)this + 56) = pguid;
    *((_DWORD *)this + 5) |= 2u;
    return 0;
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      10,
      (unsigned int)WPP_00afc214459c30232c74a98e140fe06e_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"CoCreateGuid FAILED",
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180034340  mov     [rsp+arg_8], rbx
0x180034345  push    rdi
0x180034346  sub     rsp, 50h
0x18003434a  mov     rax, cs:__security_cookie
0x180034351  xor     rax, rsp
0x180034354  mov     [rsp+58h+var_18], rax
0x180034359  mov     rdi, rcx
0x18003435c  xorps   xmm0, xmm0
0x18003435f  lea     rcx, [rsp+58h+pguid]; pguid
0x180034364  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x180034369  call    cs:__imp_CoCreateGuid
0x18003436f  mov     ebx, eax
0x180034371  test    eax, eax
0x180034373  jns     short loc_1800343CA
0x180034375  mov     rcx, cs:WPP_GLOBAL_Control
0x18003437c  lea     rax, WPP_GLOBAL_Control
0x180034383  cmp     rcx, rax
0x180034386  jz      short loc_1800343DA
0x180034388  test    byte ptr [rcx+1Ch], 8
0x18003438c  jz      short loc_1800343DA
0x18003438e  cmp     byte ptr [rcx+19h], 2
0x180034392  jb      short loc_1800343DA
0x180034394  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180034399  lea     rcx, aCocreateguidFa; "CoCreateGuid FAILED"
0x1800343a0  mov     [rsp+58h+var_30], ebx
0x1800343a4  mov     [rsp+58h+var_38], rcx
0x1800343a9  lea     r8, WPP_00afc214459c30232c74a98e140fe06e_Traceguids
0x1800343b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800343b7  mov     edx, 0Ah
0x1800343bc  mov     r9d, eax
0x1800343bf  mov     rcx, [rcx+10h]
0x1800343c3  call    WPP_SF_DsD
0x1800343c8  jmp     short loc_1800343DA
0x1800343ca  movups  xmm0, xmmword ptr [rsp+58h+pguid.Data1]
0x1800343cf  movdqu  xmmword ptr [rdi+38h], xmm0
0x1800343d4  or      dword ptr [rdi+14h], 2
0x1800343d8  xor     ebx, ebx
0x1800343da  mov     eax, ebx
0x1800343dc  mov     rcx, [rsp+58h+var_18]
0x1800343e1  xor     rcx, rsp; StackCookie
0x1800343e4  call    __security_check_cookie
0x1800343e9  mov     rbx, [rsp+58h+arg_8]
0x1800343ee  add     rsp, 50h
0x1800343f2  pop     rdi
0x1800343f3  retn
```
