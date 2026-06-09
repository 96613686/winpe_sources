# TpmBufferAccessor::Append<ushort>(ushort,void *)

- ea: `0x140010d70`
- end: `0x140010dec`
- name: `??$Append@G@TpmBufferAccessor@@QEAAJGPEAX@Z`
- size: `124`
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

- `0x140010d70`
- `0x14001a468`

## pseudocode

```c
__int64 __fastcall TpmBufferAccessor::Append<unsigned short>(__int64 *a1, __int16 a2, void *a3)
{
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  signed int i; // edx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 result; // rax
  __int16 v12; // [rsp+38h] [rbp+10h]

  v12 = a2;
  v5 = (unsigned int)(*((_DWORD *)a1 + 4) - *(_DWORD *)a1);
  if ( (int)v5 + 2 < (unsigned int)v5 )
    return 2147483653LL;
  v6 = (unsigned int)v5;
  if ( v5 + 2 > (unsigned __int64)*((unsigned int *)a1 + 2) )
    return 2147483653LL;
  v7 = *a1;
  for ( i = 0; (unsigned int)i < 2; ++i )
  {
    v9 = i;
    v10 = v6 - i;
    *(_BYTE *)(v10 + v7 + 1) = *((_BYTE *)&v12 + v9);
  }
  result = 0;
  if ( !a3 || (result = ShaHashData(a3, (unsigned __int8 *)a1[2], 2u), (int)result >= 0) )
    a1[2] += 2;
  return result;
}

```

## disassembly

```asm
0x140010d70  push    rbx
0x140010d72  sub     rsp, 20h
0x140010d76  mov     rbx, rcx
0x140010d79  mov     [rsp+28h+arg_8], dx
0x140010d7e  mov     ecx, [rcx+10h]
0x140010d81  mov     r10, r8
0x140010d84  sub     ecx, [rbx]
0x140010d86  lea     eax, [rcx+2]
0x140010d89  cmp     eax, ecx
0x140010d8b  jb      short loc_140010DCD
0x140010d8d  mov     edx, [rbx+8]
0x140010d90  lea     rax, [rcx+2]
0x140010d94  mov     r9d, ecx
0x140010d97  cmp     rax, rdx
0x140010d9a  ja      short loc_140010DCD
0x140010d9c  mov     r8, [rbx]
0x140010d9f  xor     edx, edx
0x140010da1  movsxd  rax, edx
0x140010da4  mov     rcx, r9
0x140010da7  sub     rcx, rax
0x140010daa  inc     edx
0x140010dac  mov     al, byte ptr [rsp+rax+28h+arg_8]
0x140010db0  mov     [rcx+r8+1], al
0x140010db5  cmp     edx, 2
0x140010db8  jb      short loc_140010DA1
0x140010dba  xor     eax, eax
0x140010dbc  test    r10, r10
0x140010dbf  jnz     short loc_140010DD4
0x140010dc1  add     qword ptr [rbx+10h], 2
0x140010dc6  add     rsp, 20h
0x140010dca  pop     rbx
0x140010dcb  retn
0x140010dcd  mov     eax, 80000005h
0x140010dd2  jmp     short loc_140010DC6
0x140010dd4  mov     rdx, [rbx+10h]; unsigned __int8 *
0x140010dd8  mov     r8d, 2; unsigned int
0x140010dde  mov     rcx, r10; void *
0x140010de1  call    ?ShaHashData@@YAJPEAXPEAEI@Z; ShaHashData(void *,uchar *,uint)
0x140010de6  test    eax, eax
0x140010de8  js      short loc_140010DC6
0x140010dea  jmp     short loc_140010DC1
```
