# CControlPacket::GetBLOB(ushort const *,ushort const *,ulong,void *,ulong)

- ea: `0x18001e32c`
- end: `0x18001e3e0`
- name: `?GetBLOB@CControlPacket@@QEAAKPEBG0KPEAXK@Z`
- size: `180`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001cb58`

## callees

- `0x180002692`
- `0x18001dd30`
- `0x18001e32c`
- `0x18001e528`

## string_xrefs

- `0x18001e346`: `UserSid`
- `0x18001e392`: `UserSid`

## pseudocode

```c
__int64 __fastcall CControlPacket::GetBLOB(
        CControlPacket *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        void *a5,
        size_t Size)
{
  int v7; // ebp
  unsigned int Length; // ebx
  size_t v9; // rdi
  int v11; // [rsp+20h] [rbp-38h]
  void *Src; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v13; // [rsp+70h] [rbp+18h] BYREF
  int v14; // [rsp+74h] [rbp+1Ch]

  v14 = HIDWORD(a3);
  v13 = 0;
  Src = 0;
  v7 = (int)this;
  Length = CControlPacket::GetLength(this, L"CntList", L"UserSid", a4, &v13);
  if ( !Length )
  {
    v9 = (unsigned int)Size;
    if ( (_DWORD)Size == v13 )
    {
      Length = CControlPacket::GetVariable<unsigned char>(
                 v7,
                 (unsigned int)L"CntList",
                 (unsigned int)L"UserSid",
                 a4,
                 v11,
                 1,
                 -1,
                 (__int64)&Src);
      if ( !Length )
        memmove_0(a5, Src, v9);
    }
    else
    {
      return 111;
    }
  }
  return Length;
}

```

## disassembly

```asm
0x18001e32c  mov     rax, rsp
0x18001e32f  mov     [rax+8], rbx
0x18001e333  mov     [rax+18h], r8
0x18001e337  mov     [rax+10h], rdx
0x18001e33b  push    rbp
0x18001e33c  push    rsi
0x18001e33d  push    rdi
0x18001e33e  sub     rsp, 40h
0x18001e342  and     dword ptr [rax+18h], 0
0x18001e346  lea     r8, aUsersid; "UserSid"
0x18001e34d  and     qword ptr [rax+10h], 0
0x18001e352  lea     rax, [rax+18h]
0x18001e356  lea     rdx, aCntlist; "CntList"
0x18001e35d  mov     [rsp+58h+var_38], rax; unsigned int *
0x18001e362  mov     esi, r9d
0x18001e365  mov     rbp, rcx
0x18001e368  call    ?GetLength@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetLength(ushort const *,ushort const *,ulong,ulong *)
0x18001e36d  mov     ebx, eax
0x18001e36f  test    eax, eax
0x18001e371  jnz     short loc_18001E3D0
0x18001e373  mov     edi, dword ptr [rsp+58h+Size]
0x18001e37a  cmp     edi, [rsp+58h+arg_10]
0x18001e37e  jz      short loc_18001E385
0x18001e380  lea     ebx, [rax+6Fh]
0x18001e383  jmp     short loc_18001E3D0
0x18001e385  lea     rax, [rsp+58h+Src]
0x18001e38a  mov     r9d, esi
0x18001e38d  mov     [rsp+58h+var_20], rax
0x18001e392  lea     r8, aUsersid; "UserSid"
0x18001e399  or      [rsp+58h+var_28], 0FFFFFFFFh
0x18001e39e  lea     rdx, aCntlist; "CntList"
0x18001e3a5  mov     rcx, rbp
0x18001e3a8  mov     [rsp+58h+var_30], 1
0x18001e3b0  call    ??$GetVariable@E@CControlPacket@@QEAAKPEBG0KKKKPEAPEAE@Z; CControlPacket::GetVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,ulong,uchar * *)
0x18001e3b5  mov     ebx, eax
0x18001e3b7  test    eax, eax
0x18001e3b9  jnz     short loc_18001E3D0
0x18001e3bb  mov     rdx, [rsp+58h+Src]; Src
0x18001e3c0  mov     r8, rdi; Size
0x18001e3c3  mov     rcx, [rsp+58h+arg_20]; void *
0x18001e3cb  call    memmove_0
0x18001e3d0  mov     eax, ebx
0x18001e3d2  mov     rbx, [rsp+58h+arg_0]
0x18001e3d7  add     rsp, 40h
0x18001e3db  pop     rdi
0x18001e3dc  pop     rsi
0x18001e3dd  pop     rbp
0x18001e3de  retn
```
