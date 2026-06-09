# CRemoteDevice::GetCompatId(ushort * *,ulong *)

- ea: `0x180033d30`
- end: `0x180033e11`
- name: `?GetCompatId@CRemoteDevice@@UEAAJPEAPEAGPEAK@Z`
- size: `225`
- prototype: `__int64 __fastcall(CRemoteDevice *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b8f8`
- `0x18001ba64`
- `0x180033d30`
- `0x180047ea6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033d7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033d7b`

## pseudocode

```c
__int64 __fastcall CRemoteDevice::GetCompatId(CRemoteDevice *this, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned int v6; // eax
  unsigned __int16 *v7; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  if ( !a2 || !a3 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 11) )
    return 2147549183LL;
  v6 = *((_DWORD *)this + 40);
  if ( !v6 )
    return 2147549183LL;
  *a3 = v6;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v6);
  *a2 = v7;
  if ( v7 )
  {
    memcpy_0(v7, *((const void **)this + 11), 2LL * *a3);
    return 0;
  }
  else
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        25,
        (unsigned int)WPP_00afc214459c30232c74a98e140fe06e_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"BYTE[]");
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180033d30  mov     [rsp+arg_0], rbx
0x180033d35  mov     [rsp+arg_8], rsi
0x180033d3a  push    rdi
0x180033d3b  sub     rsp, 30h
0x180033d3f  mov     rdi, r8
0x180033d42  mov     rsi, rdx
0x180033d45  mov     rbx, rcx
0x180033d48  test    rdx, rdx
0x180033d4b  jz      loc_180033DFC
0x180033d51  test    r8, r8
0x180033d54  jz      loc_180033DFC
0x180033d5a  cmp     qword ptr [rcx+58h], 0
0x180033d5f  jz      loc_180033DF5
0x180033d65  mov     eax, [rcx+0A0h]
0x180033d6b  test    eax, eax
0x180033d6d  jz      loc_180033DF5
0x180033d73  mov     ecx, eax
0x180033d75  mov     [r8], eax
0x180033d78  add     rcx, rcx; cb
0x180033d7b  call    cs:__imp_CoTaskMemAlloc
0x180033d81  mov     [rsi], rax
0x180033d84  test    rax, rax
0x180033d87  jnz     short loc_180033DDF
0x180033d89  mov     rax, cs:WPP_GLOBAL_Control
0x180033d90  lea     rcx, WPP_GLOBAL_Control
0x180033d97  cmp     rax, rcx
0x180033d9a  jz      short loc_180033DD8
0x180033d9c  test    byte ptr [rax+1Ch], 8
0x180033da0  jz      short loc_180033DD8
0x180033da2  cmp     byte ptr [rax+19h], 2
0x180033da6  jb      short loc_180033DD8
0x180033da8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033dad  lea     rcx, aByte; "BYTE[]"
0x180033db4  mov     edx, 19h
0x180033db9  mov     [rsp+38h+var_18], rcx
0x180033dbe  lea     r8, WPP_00afc214459c30232c74a98e140fe06e_Traceguids
0x180033dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180033dcc  mov     r9d, eax
0x180033dcf  mov     rcx, [rcx+10h]
0x180033dd3  call    WPP_SF_Ds
0x180033dd8  mov     eax, 8007000Eh
0x180033ddd  jmp     short loc_180033E01
0x180033ddf  mov     r8d, [rdi]
0x180033de2  mov     rcx, rax; void *
0x180033de5  mov     rdx, [rbx+58h]; Src
0x180033de9  add     r8, r8; Size
0x180033dec  call    memcpy_0
0x180033df1  xor     eax, eax
0x180033df3  jmp     short loc_180033E01
0x180033df5  mov     eax, 8000FFFFh
0x180033dfa  jmp     short loc_180033E01
0x180033dfc  mov     eax, 80004003h
0x180033e01  mov     rbx, [rsp+38h+arg_0]
0x180033e06  mov     rsi, [rsp+38h+arg_8]
0x180033e0b  add     rsp, 30h
0x180033e0f  pop     rdi
0x180033e10  retn
```
