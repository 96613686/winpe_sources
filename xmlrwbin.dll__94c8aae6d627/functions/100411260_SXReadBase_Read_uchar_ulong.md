# SXReadBase::Read(uchar *,ulong)

- ea: `0x100411260`
- end: `0x1004112da`
- name: `?Read@SXReadBase@@AEAAKPEAEK@Z`
- size: `122`
- prototype: `unsigned int __fastcall(SXReadBase *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100411160`

## callees

- `0x100401350`
- `0x100411260`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXReadBase::Read(SXReadBase *this, unsigned __int8 *a2, __int64 a3)
{
  __int64 v4; // rcx
  int v5; // eax
  __int64 result; // rax
  __int64 v7; // rcx
  unsigned int v8; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 1448) )
    return 0;
  v4 = *((_QWORD *)this + 180);
  if ( !v4 )
    return 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64, unsigned int *))(*(_QWORD *)v4 + 24LL))(
         v4,
         a2,
         a3,
         &v8);
  if ( v5 < 0 )
  {
    _mm_lfence();
    MXRRaiseException(v5);
    JUMPOUT(0x1004112D9LL);
  }
  result = v8;
  if ( !v8 )
  {
    v7 = *((_QWORD *)this + 180);
    *((_BYTE *)this + 1448) = 1;
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *((_QWORD *)this + 180) = 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x100411260  push    rbx
0x100411262  sub     rsp, 30h
0x100411266  cmp     byte ptr [rcx+5A8h], 0
0x10041126d  mov     rbx, rcx
0x100411270  jnz     short loc_1004112C7
0x100411272  mov     rcx, [rcx+5A0h]
0x100411279  test    rcx, rcx
0x10041127c  jz      short loc_1004112C7
0x10041127e  mov     rax, [rcx]
0x100411281  lea     r9, [rsp+38h+arg_0]
0x100411286  mov     rax, [rax+18h]
0x10041128a  call    cs:__guard_dispatch_icall_fptr
0x100411290  test    eax, eax
0x100411292  js      short loc_1004112CF
0x100411294  mov     eax, [rsp+38h+arg_0]
0x100411298  test    eax, eax
0x10041129a  jnz     short loc_1004112C9
0x10041129c  mov     rcx, [rbx+5A0h]
0x1004112a3  mov     byte ptr [rbx+5A8h], 1
0x1004112aa  test    rcx, rcx
0x1004112ad  jz      short loc_1004112C7
0x1004112af  mov     rax, [rcx]
0x1004112b2  mov     rax, [rax+10h]
0x1004112b6  call    cs:__guard_dispatch_icall_fptr
0x1004112bc  mov     qword ptr [rbx+5A0h], 0
0x1004112c7  xor     eax, eax
0x1004112c9  add     rsp, 30h
0x1004112cd  pop     rbx
0x1004112ce  retn
0x1004112cf  lfence
0x1004112d2  mov     ecx, eax; int
0x1004112d4  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
