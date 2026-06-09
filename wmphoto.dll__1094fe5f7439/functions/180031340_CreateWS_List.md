# CreateWS_List

- ea: `0x180031340`
- end: `0x1800313bb`
- name: `CreateWS_List`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001024`

## callees

- `0x180031340`
- `0x1800313c4`

## pseudocode

```c
__int64 __fastcall CreateWS_List(_QWORD *a1)
{
  __int64 result; // rax
  _QWORD *v3; // rdx

  result = WMPAlloc(a1, 0x1070u);
  if ( (int)result >= 0 )
  {
    v3 = (_QWORD *)*a1;
    *v3 = *a1 + 112LL;
    v3[13] = 0;
    v3[6] = CloseWS_List;
    v3[8] = ReadWS_List;
    v3[9] = WriteWS_List;
    v3[11] = SetPosWS_List;
    v3[12] = GetPosWS_List;
    v3[1] = 4096;
    v3[2] = 0;
    v3[3] = 0;
    v3[7] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180031340  push    rbx
0x180031342  sub     rsp, 20h
0x180031346  mov     edx, 1070h
0x18003134b  mov     rbx, rcx
0x18003134e  call    WMPAlloc
0x180031353  xor     r8d, r8d
0x180031356  test    eax, eax
0x180031358  js      short loc_1800313B5
0x18003135a  mov     rdx, [rbx]
0x18003135d  lea     rcx, [rdx+70h]
0x180031361  mov     [rdx], rcx
0x180031364  xor     ecx, ecx
0x180031366  mov     [rdx+68h], rcx
0x18003136a  lea     rcx, CloseWS_List
0x180031371  mov     [rdx+30h], rcx
0x180031375  lea     rcx, ReadWS_List
0x18003137c  mov     [rdx+40h], rcx
0x180031380  lea     rcx, WriteWS_List
0x180031387  mov     [rdx+48h], rcx
0x18003138b  lea     rcx, SetPosWS_List
0x180031392  mov     [rdx+58h], rcx
0x180031396  lea     rcx, GetPosWS_List
0x18003139d  mov     [rdx+60h], rcx
0x1800313a1  mov     qword ptr [rdx+8], 1000h
0x1800313a9  mov     [rdx+10h], r8
0x1800313ad  mov     [rdx+18h], r8
0x1800313b1  mov     [rdx+38h], r8
0x1800313b5  add     rsp, 20h
0x1800313b9  pop     rbx
0x1800313ba  retn
```
