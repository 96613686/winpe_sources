# TpmBufferAccessor::Append<uint>(uint,void *)

- ea: `0x140010374`
- end: `0x1400103ef`
- name: `??$Append@I@TpmBufferAccessor@@QEAAJIPEAX@Z`
- size: `123`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ae4`
- `0x14000e7b8`
- `0x14001f700`
- `0x14002015c`

## callees

- `0x140010374`
- `0x14001a468`

## pseudocode

```c
__int64 __fastcall TpmBufferAccessor::Append<unsigned int>(__int64 *a1, int a2, void *a3)
{
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  signed int i; // edx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 result; // rax
  int v12; // [rsp+38h] [rbp+10h]

  v12 = a2;
  v5 = (unsigned int)(*((_DWORD *)a1 + 4) - *(_DWORD *)a1);
  if ( (int)v5 + 4 < (unsigned int)v5 )
    return 2147483653LL;
  v6 = (unsigned int)v5;
  if ( v5 + 4 > (unsigned __int64)*((unsigned int *)a1 + 2) )
    return 2147483653LL;
  v7 = *a1;
  for ( i = 0; (unsigned int)i < 4; ++i )
  {
    v9 = i;
    v10 = v6 - i;
    *(_BYTE *)(v10 + v7 + 3) = *((_BYTE *)&v12 + v9);
  }
  result = 0;
  if ( !a3 || (result = ShaHashData(a3, (unsigned __int8 *)a1[2], 4u), (int)result >= 0) )
    a1[2] += 4;
  return result;
}

```

## disassembly

```asm
0x140010374  push    rbx
0x140010376  sub     rsp, 20h
0x14001037a  mov     rbx, rcx
0x14001037d  mov     [rsp+28h+arg_8], edx
0x140010381  mov     ecx, [rcx+10h]
0x140010384  mov     r10, r8
0x140010387  sub     ecx, [rbx]
0x140010389  lea     eax, [rcx+4]
0x14001038c  cmp     eax, ecx
0x14001038e  jb      short loc_1400103D0
0x140010390  mov     edx, [rbx+8]
0x140010393  lea     rax, [rcx+4]
0x140010397  mov     r9d, ecx
0x14001039a  cmp     rax, rdx
0x14001039d  ja      short loc_1400103D0
0x14001039f  mov     r8, [rbx]
0x1400103a2  xor     edx, edx
0x1400103a4  movsxd  rax, edx
0x1400103a7  mov     rcx, r9
0x1400103aa  sub     rcx, rax
0x1400103ad  inc     edx
0x1400103af  mov     al, byte ptr [rsp+rax+28h+arg_8]
0x1400103b3  mov     [rcx+r8+3], al
0x1400103b8  cmp     edx, 4
0x1400103bb  jb      short loc_1400103A4
0x1400103bd  xor     eax, eax
0x1400103bf  test    r10, r10
0x1400103c2  jnz     short loc_1400103D7
0x1400103c4  add     qword ptr [rbx+10h], 4
0x1400103c9  add     rsp, 20h
0x1400103cd  pop     rbx
0x1400103ce  retn
0x1400103d0  mov     eax, 80000005h
0x1400103d5  jmp     short loc_1400103C9
0x1400103d7  mov     rdx, [rbx+10h]; unsigned __int8 *
0x1400103db  mov     r8d, 4; unsigned int
0x1400103e1  mov     rcx, r10; void *
0x1400103e4  call    ?ShaHashData@@YAJPEAXPEAEI@Z; ShaHashData(void *,uchar *,uint)
0x1400103e9  test    eax, eax
0x1400103eb  js      short loc_1400103C9
0x1400103ed  jmp     short loc_1400103C4
```
