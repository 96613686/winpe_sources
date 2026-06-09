# CreateWS_List

- ea: `0x18003169c`
- end: `0x180031718`
- name: `CreateWS_List`
- size: `124`
- prototype: `__int64 __fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001024`

## callees

- `0x18003169c`
- `0x180031720`

## pseudocode

```c
__int64 __fastcall CreateWS_List(_QWORD **a1)
{
  __int64 result; // rax
  _QWORD *v3; // rdx

  result = WMPAlloc(a1, 4208);
  if ( (int)result >= 0 )
  {
    v3 = *a1;
    *v3 = *a1 + 14;
    v3[13] = 0;
    v3[6] = CloseWS_List;
    v3[8] = ReadWS_List;
    v3[9] = &WriteWS_List;
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
0x18003169c  push    rbx
0x18003169e  sub     rsp, 20h
0x1800316a2  mov     edx, 1070h
0x1800316a7  mov     rbx, rcx
0x1800316aa  call    WMPAlloc
0x1800316af  xor     r8d, r8d
0x1800316b2  test    eax, eax
0x1800316b4  js      short loc_180031711
0x1800316b6  mov     rdx, [rbx]
0x1800316b9  lea     rcx, [rdx+70h]
0x1800316bd  mov     [rdx], rcx
0x1800316c0  xor     ecx, ecx
0x1800316c2  mov     [rdx+68h], rcx
0x1800316c6  lea     rcx, CloseWS_List
0x1800316cd  mov     [rdx+30h], rcx
0x1800316d1  lea     rcx, ReadWS_List
0x1800316d8  mov     [rdx+40h], rcx
0x1800316dc  lea     rcx, WriteWS_List
0x1800316e3  mov     [rdx+48h], rcx
0x1800316e7  lea     rcx, SetPosWS_List
0x1800316ee  mov     [rdx+58h], rcx
0x1800316f2  lea     rcx, GetPosWS_List
0x1800316f9  mov     [rdx+60h], rcx
0x1800316fd  mov     qword ptr [rdx+8], 1000h
0x180031705  mov     [rdx+10h], r8
0x180031709  mov     [rdx+18h], r8
0x18003170d  mov     [rdx+38h], r8
0x180031711  add     rsp, 20h
0x180031715  pop     rbx
0x180031716  retn
```
