# CNupLayout::GetPageCoordinate(uint,_ENupDirection,uint *,uint *)

- ea: `0x180006470`
- end: `0x18000650b`
- name: `?GetPageCoordinate@CNupLayout@@QEBA_NIW4_ENupDirection@@PEAI1@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fc0`

## callees

- `0x180006470`

## pseudocode

```c
char __fastcall CNupLayout::GetPageCoordinate(unsigned int *a1, unsigned int a2, int a3, int *a4, int *a5)
{
  unsigned int v5; // r11d
  unsigned int v6; // r10d
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  int v9; // r8d
  int v10; // r8d
  char result; // al
  int v12; // r8d
  int v13; // edx
  int v14; // edx

  v5 = *a1;
  v6 = a1[1];
  v7 = *a1 * v6;
  *a4 = 0;
  *a5 = 0;
  v8 = a2 % v7;
  if ( a3 )
  {
    v9 = a3 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
          return 0;
        v12 = v8 % v5;
        v13 = v8 / v5;
      }
      else
      {
        v13 = v8 % v6;
        v12 = v8 / v6;
      }
      v14 = v6 + ~v13;
    }
    else
    {
      v12 = v8 % v5;
      v14 = v8 / v5;
    }
  }
  else
  {
    v12 = v8 / v6;
    v14 = v8 % v6;
  }
  *a4 = v14;
  result = 1;
  *a5 = v12;
  return result;
}

```

## disassembly

```asm
0x180006470  mov     [rsp+arg_0], rbx
0x180006475  mov     r11d, [rcx]
0x180006478  mov     eax, edx
0x18000647a  mov     r10d, [rcx+4]
0x18000647e  xor     edx, edx
0x180006480  mov     rbx, [rsp+arg_20]
0x180006485  mov     ecx, r10d
0x180006488  imul    ecx, r11d
0x18000648c  mov     dword ptr [r9], 0
0x180006493  mov     dword ptr [rbx], 0
0x180006499  div     ecx
0x18000649b  mov     ecx, edx
0x18000649d  test    r8d, r8d
0x1800064a0  jz      short loc_1800064EC
0x1800064a2  sub     r8d, 1
0x1800064a6  jz      short loc_1800064D7
0x1800064a8  sub     r8d, 1
0x1800064ac  jz      short loc_1800064C6
0x1800064ae  cmp     r8d, 1
0x1800064b2  jz      short loc_1800064B8
0x1800064b4  xor     al, al
0x1800064b6  jmp     short loc_180006505
0x1800064b8  xor     edx, edx
0x1800064ba  mov     eax, ecx
0x1800064bc  div     r11d
0x1800064bf  mov     r8d, edx
0x1800064c2  mov     edx, eax
0x1800064c4  jmp     short loc_1800064D0
0x1800064c6  xor     edx, edx
0x1800064c8  mov     eax, ecx
0x1800064ca  div     r10d
0x1800064cd  mov     r8d, eax
0x1800064d0  not     edx
0x1800064d2  add     edx, r10d
0x1800064d5  jmp     short loc_1800064FD
0x1800064d7  xor     edx, edx
0x1800064d9  mov     eax, ecx
0x1800064db  div     r11d
0x1800064de  mov     eax, ecx
0x1800064e0  mov     r8d, edx
0x1800064e3  xor     edx, edx
0x1800064e5  div     r11d
0x1800064e8  mov     edx, eax
0x1800064ea  jmp     short loc_1800064FD
0x1800064ec  xor     edx, edx
0x1800064ee  mov     eax, ecx
0x1800064f0  div     r10d
0x1800064f3  xor     edx, edx
0x1800064f5  mov     r8d, eax
0x1800064f8  mov     eax, ecx
0x1800064fa  div     r10d
0x1800064fd  mov     [r9], edx
0x180006500  mov     al, 1
0x180006502  mov     [rbx], r8d
0x180006505  mov     rbx, [rsp+arg_0]
0x18000650a  retn
```
