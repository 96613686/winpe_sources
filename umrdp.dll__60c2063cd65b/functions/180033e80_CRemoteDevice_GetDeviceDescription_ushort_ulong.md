# CRemoteDevice::GetDeviceDescription(ushort * *,ulong *)

- ea: `0x180033e80`
- end: `0x180033f3c`
- name: `?GetDeviceDescription@CRemoteDevice@@UEAAJPEAPEAGPEAK@Z`
- size: `188`
- prototype: `__int64 __fastcall(CRemoteDevice *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009fa8`
- `0x18000b8f8`
- `0x18001ba64`
- `0x180033e80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033ec1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033ec1`

## pseudocode

```c
__int64 __fastcall CRemoteDevice::GetDeviceDescription(CRemoteDevice *this, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 v4; // r8
  __int64 result; // rax
  __int64 v8; // rax
  unsigned int v9; // eax
  unsigned __int16 *v10; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v4 = *((_QWORD *)this + 14);
  if ( v4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v4 + 2 * v8) );
    v9 = v8 + 1;
    *a3 = v9;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v9);
    *a2 = v10;
    if ( v10 )
    {
      return StringCchCopyW(v10, *a3, *((const unsigned __int16 **)this + 14));
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
          17,
          (unsigned int)WPP_00afc214459c30232c74a98e140fe06e_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"WCHAR[]");
      }
      return 2147942414LL;
    }
  }
  else
  {
    *a2 = 0;
    result = 1;
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180033e80  push    rbx
0x180033e82  push    rbp
0x180033e83  push    rsi
0x180033e84  push    rdi
0x180033e85  sub     rsp, 38h
0x180033e89  mov     rbx, r8
0x180033e8c  xor     ebp, ebp
0x180033e8e  mov     r8, [rcx+70h]
0x180033e92  mov     rdi, rdx
0x180033e95  mov     rsi, rcx
0x180033e98  test    r8, r8
0x180033e9b  jnz     short loc_180033EAA
0x180033e9d  mov     [rdx], rbp
0x180033ea0  lea     eax, [rbp+1]
0x180033ea3  mov     [rbx], ebp
0x180033ea5  jmp     loc_180033F33
0x180033eaa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033eae  inc     rax
0x180033eb1  cmp     [r8+rax*2], bp
0x180033eb6  jnz     short loc_180033EAE
0x180033eb8  inc     eax
0x180033eba  mov     ecx, eax
0x180033ebc  add     rcx, rcx; cb
0x180033ebf  mov     [rbx], eax
0x180033ec1  call    cs:__imp_CoTaskMemAlloc
0x180033ec7  mov     [rdi], rax
0x180033eca  test    rax, rax
0x180033ecd  jnz     short loc_180033F25
0x180033ecf  mov     rax, cs:WPP_GLOBAL_Control
0x180033ed6  lea     rcx, WPP_GLOBAL_Control
0x180033edd  cmp     rax, rcx
0x180033ee0  jz      short loc_180033F1E
0x180033ee2  test    byte ptr [rax+1Ch], 8
0x180033ee6  jz      short loc_180033F1E
0x180033ee8  cmp     byte ptr [rax+19h], 2
0x180033eec  jb      short loc_180033F1E
0x180033eee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033ef3  lea     rcx, aWchar; "WCHAR[]"
0x180033efa  mov     edx, 11h
0x180033eff  mov     [rsp+58h+var_38], rcx
0x180033f04  lea     r8, WPP_00afc214459c30232c74a98e140fe06e_Traceguids
0x180033f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f12  mov     r9d, eax
0x180033f15  mov     rcx, [rcx+10h]
0x180033f19  call    WPP_SF_Ds
0x180033f1e  mov     eax, 8007000Eh
0x180033f23  jmp     short loc_180033F33
0x180033f25  mov     edx, [rbx]; unsigned __int64
0x180033f27  mov     rcx, rax; unsigned __int16 *
0x180033f2a  mov     r8, [rsi+70h]; unsigned __int16 *
0x180033f2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033f33  add     rsp, 38h
0x180033f37  pop     rdi
0x180033f38  pop     rsi
0x180033f39  pop     rbp
0x180033f3a  pop     rbx
0x180033f3b  retn
```
