# CRemoteDevice::GetIdentity(ushort * *,ulong *)

- ea: `0x1800341a0`
- end: `0x18003424a`
- name: `?GetIdentity@CRemoteDevice@@UEAAJPEAPEAGPEAK@Z`
- size: `170`
- prototype: `__int64 __fastcall(CRemoteDevice *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009fa8`
- `0x18000b8f8`
- `0x18001ba64`
- `0x1800341a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800341cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800341cf`

## pseudocode

```c
__int64 __fastcall CRemoteDevice::GetIdentity(CRemoteDevice *this, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 v3; // rax
  __int64 v5; // rcx
  unsigned int v8; // eax
  unsigned __int16 *v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v3 = -1;
  v5 = *((_QWORD *)this + 7);
  do
    ++v3;
  while ( *(_WORD *)(v5 + 2 * v3) );
  v8 = v3 + 1;
  *a3 = v8;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v8);
  *a2 = v9;
  if ( v9 )
    return StringCchCopyW(v9, *a3, *((const unsigned __int16 **)this + 7));
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      13,
      (unsigned int)WPP_00afc214459c30232c74a98e140fe06e_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"WCHAR[]");
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800341a0  push    rbx
0x1800341a2  push    rbp
0x1800341a3  push    rsi
0x1800341a4  push    rdi
0x1800341a5  sub     rsp, 38h
0x1800341a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800341ad  mov     rdi, rcx
0x1800341b0  mov     rcx, [rcx+38h]
0x1800341b4  xor     ebp, ebp
0x1800341b6  mov     rbx, r8
0x1800341b9  mov     rsi, rdx
0x1800341bc  inc     rax
0x1800341bf  cmp     [rcx+rax*2], bp
0x1800341c3  jnz     short loc_1800341BC
0x1800341c5  inc     eax
0x1800341c7  mov     ecx, eax
0x1800341c9  add     rcx, rcx; cb
0x1800341cc  mov     [r8], eax
0x1800341cf  call    cs:__imp_CoTaskMemAlloc
0x1800341d5  mov     [rsi], rax
0x1800341d8  test    rax, rax
0x1800341db  jnz     short loc_180034233
0x1800341dd  mov     rax, cs:WPP_GLOBAL_Control
0x1800341e4  lea     rcx, WPP_GLOBAL_Control
0x1800341eb  cmp     rax, rcx
0x1800341ee  jz      short loc_18003422C
0x1800341f0  test    byte ptr [rax+1Ch], 8
0x1800341f4  jz      short loc_18003422C
0x1800341f6  cmp     byte ptr [rax+19h], 2
0x1800341fa  jb      short loc_18003422C
0x1800341fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180034201  lea     rcx, aWchar; "WCHAR[]"
0x180034208  mov     edx, 0Dh
0x18003420d  mov     [rsp+58h+var_38], rcx
0x180034212  lea     r8, WPP_00afc214459c30232c74a98e140fe06e_Traceguids
0x180034219  mov     rcx, cs:WPP_GLOBAL_Control
0x180034220  mov     r9d, eax
0x180034223  mov     rcx, [rcx+10h]
0x180034227  call    WPP_SF_Ds
0x18003422c  mov     eax, 8007000Eh
0x180034231  jmp     short loc_180034241
0x180034233  mov     edx, [rbx]; unsigned __int64
0x180034235  mov     rcx, rax; unsigned __int16 *
0x180034238  mov     r8, [rdi+38h]; unsigned __int16 *
0x18003423c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034241  add     rsp, 38h
0x180034245  pop     rdi
0x180034246  pop     rsi
0x180034247  pop     rbp
0x180034248  pop     rbx
0x180034249  retn
```
