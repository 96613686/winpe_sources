# CWdsInProcDeviceControllerClient::DeleteDevice(ushort const *)

- ea: `0x180014050`
- end: `0x18001419d`
- name: `?DeleteDevice@CWdsInProcDeviceControllerClient@@UEAAKPEBG@Z`
- size: `333`
- prototype: `unsigned int(CWdsInProcDeviceControllerClient *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800121ac`
- `0x180012214`
- `0x180014050`
- `0x180014c40`
- `0x180014d10`
- `0x180014f24`
- `0x180016020`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CWdsInProcDeviceControllerClient::DeleteDevice(
        CWdsInProcDeviceControllerClient *this,
        const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int128 v17; // [rsp+30h] [rbp-29h] BYREF
  __int64 v18; // [rsp+40h] [rbp-19h]
  int v19; // [rsp+48h] [rbp-11h]
  int v20; // [rsp+50h] [rbp-9h]
  int v21; // [rsp+54h] [rbp-5h]
  int v22; // [rsp+58h] [rbp-1h]
  __int128 v23; // [rsp+60h] [rbp+7h] BYREF
  __int64 v24; // [rsp+70h] [rbp+17h]
  int v25; // [rsp+78h] [rbp+1Fh]
  int v26; // [rsp+80h] [rbp+27h]
  int v27; // [rsp+84h] [rbp+2Bh]
  int v28; // [rsp+88h] [rbp+2Fh]

  v20 = 0;
  v22 = 0;
  v21 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v4 = CControlPacket::SendInitialize((CControlPacket *)&v17, 0, 5u, 1u);
  if ( !(unsigned int)ElValidateWin32_10(v4, v5, v6, 0x1CEu) )
  {
    v4 = CControlPacket::SendInitialize((CControlPacket *)&v23, 0, 0, 2u);
    if ( !(unsigned int)ElValidateWin32_10(v4, v7, v8, 0x1D2u) )
    {
      v4 = CWdsDeviceControllerPacket::AddDevice((CWdsDeviceControllerPacket *)&v17, a2);
      if ( !(unsigned int)ElValidateWin32_10(v4, v9, v10, 0x1D5u) )
      {
        v11 = (const unsigned __int16 *)*((_QWORD *)this + 6);
        if ( !v11
          || (v4 = CWdsDeviceControllerPacket::AddManagementController((CWdsDeviceControllerPacket *)&v17, v11),
              !(unsigned int)ElValidateWin32_10(v4, v12, v13, 0x1DAu)) )
        {
          v4 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, __int128 *))this + 5))(
                 *((_QWORD *)this + 1),
                 *((_QWORD *)this + 2),
                 *((_QWORD *)this + 3),
                 &v17,
                 &v23);
          ElValidateWin32_10(v4, v14, v15, 0x1E2u);
        }
      }
    }
  }
  CControlPacket::Shutdown((CControlPacket *)&v23);
  CControlPacket::Shutdown((CControlPacket *)&v17);
  return v4;
}

```

## disassembly

```asm
0x180014050  mov     [rsp-8+arg_10], rbx
0x180014055  push    rbp
0x180014056  push    rsi
0x180014057  push    rdi
0x180014058  lea     rbp, [rsp-47h]
0x18001405d  sub     rsp, 0A0h
0x180014064  mov     rax, cs:__security_cookie
0x18001406b  xor     rax, rsp
0x18001406e  mov     [rbp+57h+var_20], rax
0x180014072  xor     eax, eax
0x180014074  xorps   xmm0, xmm0
0x180014077  and     [rbp+57h+var_60], eax
0x18001407a  mov     rsi, rdx
0x18001407d  and     [rbp+57h+var_58], eax
0x180014080  mov     rdi, rcx
0x180014083  and     [rbp+57h+var_5C], eax
0x180014086  lea     rcx, [rbp+57h+var_80]; this
0x18001408a  and     [rbp+57h+var_30], eax
0x18001408d  lea     r8d, [rax+5]; unsigned int
0x180014091  and     [rbp+57h+var_28], eax
0x180014094  mov     r9b, 1; unsigned __int8
0x180014097  and     [rbp+57h+var_2C], eax
0x18001409a  xor     edx, edx; void *
0x18001409c  movdqu  [rbp+57h+var_80], xmm0
0x1800140a1  mov     [rbp+57h+var_70], rax
0x1800140a5  mov     [rbp+57h+var_68], eax
0x1800140a8  movdqu  [rbp+57h+var_50], xmm0
0x1800140ad  mov     [rbp+57h+var_40], rax
0x1800140b1  mov     [rbp+57h+var_38], eax
0x1800140b4  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z; CControlPacket::SendInitialize(void *,ulong,uchar)
0x1800140b9  mov     r9d, 1CEh
0x1800140bf  mov     ecx, eax
0x1800140c1  mov     ebx, eax
0x1800140c3  call    ElValidateWin32_10
0x1800140c8  test    eax, eax
0x1800140ca  jnz     loc_180014169
0x1800140d0  mov     r9b, 2; unsigned __int8
0x1800140d3  lea     rcx, [rbp+57h+var_50]; this
0x1800140d7  xor     r8d, r8d; unsigned int
0x1800140da  xor     edx, edx; void *
0x1800140dc  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z; CControlPacket::SendInitialize(void *,ulong,uchar)
0x1800140e1  mov     r9d, 1D2h
0x1800140e7  mov     ecx, eax
0x1800140e9  mov     ebx, eax
0x1800140eb  call    ElValidateWin32_10
0x1800140f0  test    eax, eax
0x1800140f2  jnz     short loc_180014169
0x1800140f4  mov     rdx, rsi; unsigned __int16 *
0x1800140f7  lea     rcx, [rbp+57h+var_80]; this
0x1800140fb  call    ?AddDevice@CWdsDeviceControllerPacket@@QEAAKPEBG@Z; CWdsDeviceControllerPacket::AddDevice(ushort const *)
0x180014100  mov     r9d, 1D5h
0x180014106  mov     ecx, eax
0x180014108  mov     ebx, eax
0x18001410a  call    ElValidateWin32_10
0x18001410f  test    eax, eax
0x180014111  jnz     short loc_180014169
0x180014113  mov     rdx, [rdi+30h]; unsigned __int16 *
0x180014117  test    rdx, rdx
0x18001411a  jz      short loc_180014138
0x18001411c  lea     rcx, [rbp+57h+var_80]; this
0x180014120  call    ?AddManagementController@CWdsDeviceControllerPacket@@QEAAKPEBG@Z; CWdsDeviceControllerPacket::AddManagementController(ushort const *)
0x180014125  mov     r9d, 1DAh
0x18001412b  mov     ecx, eax
0x18001412d  mov     ebx, eax
0x18001412f  call    ElValidateWin32_10
0x180014134  test    eax, eax
0x180014136  jnz     short loc_180014169
0x180014138  mov     r8, [rdi+18h]
0x18001413c  lea     rax, [rbp+57h+var_50]
0x180014140  mov     rdx, [rdi+10h]
0x180014144  lea     r9, [rbp+57h+var_80]
0x180014148  mov     rcx, [rdi+8]
0x18001414c  mov     [rsp+0B0h+var_90], rax
0x180014151  mov     rax, [rdi+28h]
0x180014155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001415a  mov     r9d, 1E2h
0x180014160  mov     ecx, eax
0x180014162  mov     ebx, eax
0x180014164  call    ElValidateWin32_10
0x180014169  lea     rcx, [rbp+57h+var_50]; this
0x18001416d  call    ?Shutdown@CControlPacket@@QEAAKXZ; CControlPacket::Shutdown(void)
0x180014172  lea     rcx, [rbp+57h+var_80]; this
0x180014176  call    ?Shutdown@CControlPacket@@QEAAKXZ; CControlPacket::Shutdown(void)
0x18001417b  mov     eax, ebx
0x18001417d  mov     rcx, [rbp+57h+var_20]
0x180014181  xor     rcx, rsp; StackCookie
0x180014184  call    __security_check_cookie
0x180014189  mov     rbx, [rsp+0B0h+arg_10]
0x180014191  add     rsp, 0A0h
0x180014198  pop     rdi
0x180014199  pop     rsi
0x18001419a  pop     rbp
0x18001419b  retn
```
