# HUBID_BuildCompatibleID

- ea: `0x14001e124`
- end: `0x14001e206`
- name: `HUBID_BuildCompatibleID`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001b15c`
- `0x14007ea48`

## callees

- `0x14001dc30`
- `0x14001dce0`
- `0x14001e124`
- `0x14001e6d0`
- `0x14001ec90`
- `0x14001ef20`
- `0x140045530`

## pseudocode

```c
NTSTATUS __fastcall HUBID_BuildCompatibleID(__int64 a1, __int64 a2, _OWORD *a3, __int64 a4)
{
  __int64 v4; // r10
  __int64 *UnknownId; // rcx
  int v7; // eax
  __int64 v8; // [rsp+20h] [rbp-78h] BYREF
  __int128 *v9; // [rsp+28h] [rbp-70h]
  __int128 v10; // [rsp+30h] [rbp-68h] BYREF
  __int128 v11; // [rsp+40h] [rbp-58h]
  __int128 v12; // [rsp+50h] [rbp-48h]
  __int128 v13; // [rsp+60h] [rbp-38h]
  int v14; // [rsp+70h] [rbp-28h]

  v4 = a2;
  v10 = *(_OWORD *)L"USB\\Class_11&SubClass_00&Prot_00";
  v11 = *(_OWORD *)L"s_11&SubClass_00&Prot_00";
  v14 = *(_DWORD *)L"";
  v12 = *(_OWORD *)L"Class_00&Prot_00";
  v13 = *(_OWORD *)L"&Prot_00";
  v8 = 4456514;
  v9 = &v10;
  if ( a3 )
    *a3 = 0;
  if ( (*(_DWORD *)(a1 + 1644) & 0x2002) == 0 )
  {
    UnknownId = (__int64 *)HUBID_GetUnknownId(
                             a1,
                             a2,
                             a3,
                             a4,
                             v8,
                             v9,
                             v10,
                             *((_QWORD *)&v10 + 1),
                             v11,
                             *((_QWORD *)&v11 + 1),
                             v12);
    return HUBID_AssignIDString(UnknownId, 2, v4, a3);
  }
  v7 = *(_DWORD *)(a1 + 1640);
  if ( (v7 & 4) != 0 )
    return HUBID_BuildDeviceCompatibleID(a1, a2, a3);
  if ( (v7 & 2) != 0 )
    return HUBID_BuildHubCompatibleID(
             a1,
             a2,
             a3,
             a4,
             v8,
             v9,
             v10,
             *((_QWORD *)&v10 + 1),
             v11,
             *((_QWORD *)&v11 + 1),
             v12);
  if ( (v7 & 0x20000) != 0 )
  {
    UnknownId = &v8;
    return HUBID_AssignIDString(UnknownId, 2, v4, a3);
  }
  return HUBID_BuildClassCompatibleID(a1, a2, a3);
}

```

## disassembly

```asm
0x14001e124  sub     rsp, 98h
0x14001e12b  mov     rax, cs:__security_cookie
0x14001e132  xor     rax, rsp
0x14001e135  mov     [rsp+98h+var_18], rax
0x14001e13d  movaps  xmm0, xmmword ptr cs:aUsbClass11Subc; "USB\\Class_11&SubClass_00&Prot_00"
0x14001e144  mov     r10, rdx
0x14001e147  movaps  xmm1, xmmword ptr cs:aUsbClass11Subc+10h; "s_11&SubClass_00&Prot_00"
0x14001e14e  mov     eax, dword ptr cs:aUsbClass11Subc+40h; ""
0x14001e154  movaps  [rsp+98h+var_68], xmm0
0x14001e159  movaps  xmm0, xmmword ptr cs:aUsbClass11Subc+20h; "Class_00&Prot_00"
0x14001e160  movaps  [rsp+98h+var_58], xmm1
0x14001e165  movaps  xmm1, xmmword ptr cs:aUsbClass11Subc+30h; "&Prot_00"
0x14001e16c  mov     [rsp+98h+var_28], eax
0x14001e170  lea     rax, [rsp+98h+var_68]
0x14001e175  movaps  [rsp+98h+var_48], xmm0
0x14001e17a  movaps  [rsp+98h+var_38], xmm1
0x14001e17f  mov     [rsp+98h+var_78], 440042h
0x14001e188  mov     [rsp+98h+var_70], rax
0x14001e18d  test    r8, r8
0x14001e190  jz      short loc_14001E199
0x14001e192  xorps   xmm0, xmm0
0x14001e195  movups  xmmword ptr [r8], xmm0
0x14001e199  test    dword ptr [rcx+66Ch], 2002h
0x14001e1a3  jnz     short loc_14001E1BF
0x14001e1a5  call    HUBID_GetUnknownId
0x14001e1aa  mov     rcx, rax
0x14001e1ad  mov     r9, r8
0x14001e1b0  mov     edx, 2
0x14001e1b5  mov     r8, r10
0x14001e1b8  call    HUBID_AssignIDString
0x14001e1bd  jmp     short loc_14001E1ED
0x14001e1bf  mov     eax, [rcx+668h]
0x14001e1c5  test    al, 4
0x14001e1c7  jz      short loc_14001E1D0
0x14001e1c9  call    HUBID_BuildDeviceCompatibleID
0x14001e1ce  jmp     short loc_14001E1ED
0x14001e1d0  test    al, 2
0x14001e1d2  jz      short loc_14001E1DB
0x14001e1d4  call    HUBID_BuildHubCompatibleID
0x14001e1d9  jmp     short loc_14001E1ED
0x14001e1db  bt      eax, 11h
0x14001e1df  jnb     short loc_14001E1E8
0x14001e1e1  lea     rcx, [rsp+98h+var_78]
0x14001e1e6  jmp     short loc_14001E1AD
0x14001e1e8  call    HUBID_BuildClassCompatibleID
0x14001e1ed  mov     rcx, [rsp+98h+var_18]
0x14001e1f5  xor     rcx, rsp; StackCookie
0x14001e1f8  call    __security_check_cookie
0x14001e1fd  add     rsp, 98h
0x14001e204  retn
```
