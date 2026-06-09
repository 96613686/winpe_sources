# CRemoteDevice::GetDeviceLocation(ushort * *,ulong *)

- ea: `0x180033f50`
- end: `0x180033ffa`
- name: `?GetDeviceLocation@CRemoteDevice@@UEAAJPEAPEAGPEAK@Z`
- size: `170`
- prototype: `__int64 __fastcall(CRemoteDevice *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009fa8`
- `0x18000b8f8`
- `0x18001ba64`
- `0x180033f50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033f7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033f7f`

## pseudocode

```c
__int64 __fastcall CRemoteDevice::GetDeviceLocation(CRemoteDevice *this, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 v3; // rax
  __int64 v5; // rcx
  unsigned int v8; // eax
  unsigned __int16 *v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v3 = -1;
  v5 = *((_QWORD *)this + 12);
  do
    ++v3;
  while ( *(_WORD *)(v5 + 2 * v3) );
  v8 = v3 + 1;
  *a3 = v8;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v8);
  *a2 = v9;
  if ( v9 )
    return StringCchCopyW(v9, *a3, *((const unsigned __int16 **)this + 12));
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      23,
      (unsigned int)WPP_00afc214459c30232c74a98e140fe06e_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"WCHAR[]");
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180033f50  push    rbx
0x180033f52  push    rbp
0x180033f53  push    rsi
0x180033f54  push    rdi
0x180033f55  sub     rsp, 38h
0x180033f59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033f5d  mov     rdi, rcx
0x180033f60  mov     rcx, [rcx+60h]
0x180033f64  xor     ebp, ebp
0x180033f66  mov     rbx, r8
0x180033f69  mov     rsi, rdx
0x180033f6c  inc     rax
0x180033f6f  cmp     [rcx+rax*2], bp
0x180033f73  jnz     short loc_180033F6C
0x180033f75  inc     eax
0x180033f77  mov     ecx, eax
0x180033f79  add     rcx, rcx; cb
0x180033f7c  mov     [r8], eax
0x180033f7f  call    cs:__imp_CoTaskMemAlloc
0x180033f85  mov     [rsi], rax
0x180033f88  test    rax, rax
0x180033f8b  jnz     short loc_180033FE3
0x180033f8d  mov     rax, cs:WPP_GLOBAL_Control
0x180033f94  lea     rcx, WPP_GLOBAL_Control
0x180033f9b  cmp     rax, rcx
0x180033f9e  jz      short loc_180033FDC
0x180033fa0  test    byte ptr [rax+1Ch], 8
0x180033fa4  jz      short loc_180033FDC
0x180033fa6  cmp     byte ptr [rax+19h], 2
0x180033faa  jb      short loc_180033FDC
0x180033fac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033fb1  lea     rcx, aWchar; "WCHAR[]"
0x180033fb8  mov     edx, 17h
0x180033fbd  mov     [rsp+58h+var_38], rcx
0x180033fc2  lea     r8, WPP_00afc214459c30232c74a98e140fe06e_Traceguids
0x180033fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fd0  mov     r9d, eax
0x180033fd3  mov     rcx, [rcx+10h]
0x180033fd7  call    WPP_SF_Ds
0x180033fdc  mov     eax, 8007000Eh
0x180033fe1  jmp     short loc_180033FF1
0x180033fe3  mov     edx, [rbx]; unsigned __int64
0x180033fe5  mov     rcx, rax; unsigned __int16 *
0x180033fe8  mov     r8, [rdi+60h]; unsigned __int16 *
0x180033fec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033ff1  add     rsp, 38h
0x180033ff5  pop     rdi
0x180033ff6  pop     rsi
0x180033ff7  pop     rbp
0x180033ff8  pop     rbx
0x180033ff9  retn
```
