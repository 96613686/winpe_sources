# CRemoteDevice::GetHardwareId(ushort * *,ulong *)

- ea: `0x1800340b0`
- end: `0x180034191`
- name: `?GetHardwareId@CRemoteDevice@@UEAAJPEAPEAGPEAK@Z`
- size: `225`
- prototype: `__int64 __fastcall(CRemoteDevice *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b8f8`
- `0x18001ba64`
- `0x1800340b0`
- `0x180047ea6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800340fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800340fb`

## pseudocode

```c
__int64 __fastcall CRemoteDevice::GetHardwareId(CRemoteDevice *this, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned int v6; // eax
  unsigned __int16 *v7; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  if ( !a2 || !a3 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 8) )
    return 2147549183LL;
  v6 = *((_DWORD *)this + 39);
  if ( !v6 )
    return 2147549183LL;
  *a3 = v6;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v6);
  *a2 = v7;
  if ( v7 )
  {
    memcpy_0(v7, *((const void **)this + 8), 2LL * *a3);
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
        15,
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
0x1800340b0  mov     [rsp+arg_0], rbx
0x1800340b5  mov     [rsp+arg_8], rsi
0x1800340ba  push    rdi
0x1800340bb  sub     rsp, 30h
0x1800340bf  mov     rdi, r8
0x1800340c2  mov     rsi, rdx
0x1800340c5  mov     rbx, rcx
0x1800340c8  test    rdx, rdx
0x1800340cb  jz      loc_18003417C
0x1800340d1  test    r8, r8
0x1800340d4  jz      loc_18003417C
0x1800340da  cmp     qword ptr [rcx+40h], 0
0x1800340df  jz      loc_180034175
0x1800340e5  mov     eax, [rcx+9Ch]
0x1800340eb  test    eax, eax
0x1800340ed  jz      loc_180034175
0x1800340f3  mov     ecx, eax
0x1800340f5  mov     [r8], eax
0x1800340f8  add     rcx, rcx; cb
0x1800340fb  call    cs:__imp_CoTaskMemAlloc
0x180034101  mov     [rsi], rax
0x180034104  test    rax, rax
0x180034107  jnz     short loc_18003415F
0x180034109  mov     rax, cs:WPP_GLOBAL_Control
0x180034110  lea     rcx, WPP_GLOBAL_Control
0x180034117  cmp     rax, rcx
0x18003411a  jz      short loc_180034158
0x18003411c  test    byte ptr [rax+1Ch], 8
0x180034120  jz      short loc_180034158
0x180034122  cmp     byte ptr [rax+19h], 2
0x180034126  jb      short loc_180034158
0x180034128  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003412d  lea     rcx, aByte; "BYTE[]"
0x180034134  mov     edx, 0Fh
0x180034139  mov     [rsp+38h+var_18], rcx
0x18003413e  lea     r8, WPP_00afc214459c30232c74a98e140fe06e_Traceguids
0x180034145  mov     rcx, cs:WPP_GLOBAL_Control
0x18003414c  mov     r9d, eax
0x18003414f  mov     rcx, [rcx+10h]
0x180034153  call    WPP_SF_Ds
0x180034158  mov     eax, 8007000Eh
0x18003415d  jmp     short loc_180034181
0x18003415f  mov     r8d, [rdi]
0x180034162  mov     rcx, rax; void *
0x180034165  mov     rdx, [rbx+40h]; Src
0x180034169  add     r8, r8; Size
0x18003416c  call    memcpy_0
0x180034171  xor     eax, eax
0x180034173  jmp     short loc_180034181
0x180034175  mov     eax, 8000FFFFh
0x18003417a  jmp     short loc_180034181
0x18003417c  mov     eax, 80004003h
0x180034181  mov     rbx, [rsp+38h+arg_0]
0x180034186  mov     rsi, [rsp+38h+arg_8]
0x18003418b  add     rsp, 30h
0x18003418f  pop     rdi
0x180034190  retn
```
