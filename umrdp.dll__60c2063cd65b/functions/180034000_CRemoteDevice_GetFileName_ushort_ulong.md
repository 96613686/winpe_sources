# CRemoteDevice::GetFileName(ushort * *,ulong *)

- ea: `0x180034000`
- end: `0x1800340aa`
- name: `?GetFileName@CRemoteDevice@@UEAAJPEAPEAGPEAK@Z`
- size: `170`
- prototype: `__int64 __fastcall(CRemoteDevice *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009fa8`
- `0x18000b8f8`
- `0x18001ba64`
- `0x180034000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003402f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003402f`

## pseudocode

```c
__int64 __fastcall CRemoteDevice::GetFileName(CRemoteDevice *this, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 v3; // rax
  __int64 v5; // rcx
  unsigned int v8; // eax
  unsigned __int16 *v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v3 = -1;
  v5 = *((_QWORD *)this + 13);
  do
    ++v3;
  while ( *(_WORD *)(v5 + 2 * v3) );
  v8 = v3 + 1;
  *a3 = v8;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v8);
  *a2 = v9;
  if ( v9 )
    return StringCchCopyW(v9, *a3, *((const unsigned __int16 **)this + 13));
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      19,
      (unsigned int)WPP_00afc214459c30232c74a98e140fe06e_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"WCHAR[]");
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180034000  push    rbx
0x180034002  push    rbp
0x180034003  push    rsi
0x180034004  push    rdi
0x180034005  sub     rsp, 38h
0x180034009  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003400d  mov     rdi, rcx
0x180034010  mov     rcx, [rcx+68h]
0x180034014  xor     ebp, ebp
0x180034016  mov     rbx, r8
0x180034019  mov     rsi, rdx
0x18003401c  inc     rax
0x18003401f  cmp     [rcx+rax*2], bp
0x180034023  jnz     short loc_18003401C
0x180034025  inc     eax
0x180034027  mov     ecx, eax
0x180034029  add     rcx, rcx; cb
0x18003402c  mov     [r8], eax
0x18003402f  call    cs:__imp_CoTaskMemAlloc
0x180034035  mov     [rsi], rax
0x180034038  test    rax, rax
0x18003403b  jnz     short loc_180034093
0x18003403d  mov     rax, cs:WPP_GLOBAL_Control
0x180034044  lea     rcx, WPP_GLOBAL_Control
0x18003404b  cmp     rax, rcx
0x18003404e  jz      short loc_18003408C
0x180034050  test    byte ptr [rax+1Ch], 8
0x180034054  jz      short loc_18003408C
0x180034056  cmp     byte ptr [rax+19h], 2
0x18003405a  jb      short loc_18003408C
0x18003405c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180034061  lea     rcx, aWchar; "WCHAR[]"
0x180034068  mov     edx, 13h
0x18003406d  mov     [rsp+58h+var_38], rcx
0x180034072  lea     r8, WPP_00afc214459c30232c74a98e140fe06e_Traceguids
0x180034079  mov     rcx, cs:WPP_GLOBAL_Control
0x180034080  mov     r9d, eax
0x180034083  mov     rcx, [rcx+10h]
0x180034087  call    WPP_SF_Ds
0x18003408c  mov     eax, 8007000Eh
0x180034091  jmp     short loc_1800340A1
0x180034093  mov     edx, [rbx]; unsigned __int64
0x180034095  mov     rcx, rax; unsigned __int16 *
0x180034098  mov     r8, [rdi+68h]; unsigned __int16 *
0x18003409c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800340a1  add     rsp, 38h
0x1800340a5  pop     rdi
0x1800340a6  pop     rsi
0x1800340a7  pop     rbp
0x1800340a8  pop     rbx
0x1800340a9  retn
```
