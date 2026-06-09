# EventXmlDump::OnPropertyFound(EventDumpWorkspace *,_EVENT_DUMP_DATA *,ushort,ushort)

- ea: `0x140011030`
- end: `0x14001110d`
- name: `?OnPropertyFound@EventXmlDump@@UEAAKPEAVEventDumpWorkspace@@PEAU_EVENT_DUMP_DATA@@GG@Z`
- size: `221`
- prototype: `unsigned int __fastcall(EventXmlDump *__hidden this, struct EventDumpWorkspace *, struct _EVENT_DUMP_DATA *, unsigned __int16, unsigned __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140011030`
- `0x140032488`

## pseudocode

```c
__int64 __fastcall EventXmlDump::OnPropertyFound(
        EventXmlDump *this,
        struct EventDumpWorkspace *a2,
        unsigned __int16 **a3,
        unsigned __int16 a4,
        unsigned __int16 a5)
{
  __int64 v7; // rcx
  unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // edx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // edx

  v7 = *((_QWORD *)this + 52);
  if ( !v7 )
    goto LABEL_8;
  v9 = *a3;
  v10 = v7 - (_QWORD)*a3;
  do
  {
    v11 = *(unsigned __int16 *)((char *)v9 + v10);
    v12 = *v9 - v11;
    if ( v12 )
      break;
    ++v9;
  }
  while ( v11 );
  if ( v12 )
  {
LABEL_8:
    v13 = *((_QWORD *)this + 86);
    if ( !v13 )
      return 0;
    v14 = *a3;
    v15 = v13 - (_QWORD)*a3;
    do
    {
      v16 = *(unsigned __int16 *)((char *)v14 + v15);
      v17 = *v14 - v16;
      if ( v17 )
        break;
      ++v14;
    }
    while ( v16 );
    if ( v17 )
      return 0;
    if ( a5 == 16 )
    {
      CpdiGuidToString((unsigned __int16 *)this + 352, 0x80u, (struct _GUID *)(*(_QWORD *)(*(_QWORD *)a2 + 96LL) + a4));
      *((_QWORD *)this + 87) = (char *)this + 704;
      return 0;
    }
    return 13;
  }
  if ( a5 != 16 )
    return 13;
  CpdiGuidToString((unsigned __int16 *)this + 216, 0x80u, (struct _GUID *)(*(_QWORD *)(*(_QWORD *)a2 + 96LL) + a4));
  *((_QWORD *)this + 53) = (char *)this + 432;
  return 0;
}

```

## disassembly

```asm
0x140011030  mov     [rsp+arg_0], rbx
0x140011035  push    rdi
0x140011036  sub     rsp, 20h
0x14001103a  mov     rdi, rcx
0x14001103d  mov     r10, r8
0x140011040  mov     rcx, [rcx+1A0h]
0x140011047  mov     r11, rdx
0x14001104a  test    rcx, rcx
0x14001104d  jz      short loc_14001109F
0x14001104f  mov     rax, [r8]
0x140011052  sub     rcx, rax
0x140011055  movzx   edx, word ptr [rax]
0x140011058  movzx   r8d, word ptr [rax+rcx]
0x14001105d  sub     edx, r8d
0x140011060  jnz     short loc_14001106B
0x140011062  add     rax, 2
0x140011066  test    r8d, r8d
0x140011069  jnz     short loc_140011055
0x14001106b  test    edx, edx
0x14001106d  jnz     short loc_14001109F
0x14001106f  cmp     [rsp+28h+arg_20], 10h
0x140011075  jnz     short loc_1400110D3
0x140011077  mov     rax, [r11]
0x14001107a  lea     rbx, [rdi+1B0h]
0x140011081  movzx   r8d, r9w
0x140011085  mov     edx, 80h; unsigned int
0x14001108a  mov     rcx, rbx; unsigned __int16 *
0x14001108d  add     r8, [rax+60h]; struct _GUID *
0x140011091  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x140011096  mov     [rdi+1A8h], rbx
0x14001109d  jmp     short loc_140011100
0x14001109f  mov     rcx, [rdi+2B0h]
0x1400110a6  test    rcx, rcx
0x1400110a9  jz      short loc_140011100
0x1400110ab  mov     rax, [r10]
0x1400110ae  sub     rcx, rax
0x1400110b1  movzx   edx, word ptr [rax]
0x1400110b4  movzx   r8d, word ptr [rax+rcx]
0x1400110b9  sub     edx, r8d
0x1400110bc  jnz     short loc_1400110C7
0x1400110be  add     rax, 2
0x1400110c2  test    r8d, r8d
0x1400110c5  jnz     short loc_1400110B1
0x1400110c7  test    edx, edx
0x1400110c9  jnz     short loc_140011100
0x1400110cb  cmp     [rsp+28h+arg_20], 10h
0x1400110d1  jz      short loc_1400110DA
0x1400110d3  mov     eax, 0Dh
0x1400110d8  jmp     short loc_140011102
0x1400110da  mov     rax, [r11]
0x1400110dd  lea     rbx, [rdi+2C0h]
0x1400110e4  movzx   r8d, r9w
0x1400110e8  mov     edx, 80h; unsigned int
0x1400110ed  mov     rcx, rbx; unsigned __int16 *
0x1400110f0  add     r8, [rax+60h]; struct _GUID *
0x1400110f4  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x1400110f9  mov     [rdi+2B8h], rbx
0x140011100  xor     eax, eax
0x140011102  mov     rbx, [rsp+28h+arg_0]
0x140011107  add     rsp, 20h
0x14001110b  pop     rdi
0x14001110c  retn
```
