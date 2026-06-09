# CShareWithList::SetAutoAllowDevices(int,int)

- ea: `0x18000d810`
- end: `0x18000d8c7`
- name: `?SetAutoAllowDevices@CShareWithList@@QEAAJHH@Z`
- size: `183`
- prototype: `__int64 __fastcall(CShareWithList *__hidden this, int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d514`
- `0x18000ec90`
- `0x18000f020`
- `0x1800120ec`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000d810`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CShareWithList::SetAutoAllowDevices(CShareWithList *this, __int64 a2, int a3)
{
  int v4; // ebp
  _UNKNOWN **v6; // rcx
  __int64 v7; // r9
  int v8; // ebx

  v4 = a2;
  v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x96u, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  v7 = *((_QWORD *)this + 5);
  if ( v7 )
  {
    v8 = 0;
    if ( !v4
      || (LOWORD(a2) = -(a3 != 0),
          v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v7 + 64LL))(*((_QWORD *)this + 5), a2),
          v8 >= 0) )
    {
      *((_DWORD *)this + 32) = a3;
    }
    v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_d((TRACEHANDLE)v6[2], 0x97u, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d810  push    rbx
0x18000d812  push    rbp
0x18000d813  push    rsi
0x18000d814  push    rdi
0x18000d815  push    r14
0x18000d817  sub     rsp, 20h
0x18000d81b  mov     esi, r8d
0x18000d81e  mov     ebp, edx
0x18000d820  mov     rdi, rcx
0x18000d823  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d82a  lea     r14, WPP_GLOBAL_Control
0x18000d831  cmp     rcx, r14
0x18000d834  jz      short loc_18000D858
0x18000d836  test    byte ptr [rcx+1Ch], 20h
0x18000d83a  jz      short loc_18000D858
0x18000d83c  mov     rcx, [rcx+10h]
0x18000d840  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000d847  mov     edx, 96h
0x18000d84c  call    WPP_SF_
0x18000d851  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d858  mov     r9, [rdi+28h]
0x18000d85c  test    r9, r9
0x18000d85f  jz      short loc_18000D892
0x18000d861  xor     ebx, ebx
0x18000d863  test    ebp, ebp
0x18000d865  jz      short loc_18000D883
0x18000d867  mov     r8, [r9]
0x18000d86a  mov     eax, esi
0x18000d86c  neg     eax
0x18000d86e  mov     rcx, r9
0x18000d871  sbb     dx, dx
0x18000d874  mov     rax, [r8+40h]
0x18000d878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d87d  mov     ebx, eax
0x18000d87f  test    eax, eax
0x18000d881  js      short loc_18000D889
0x18000d883  mov     [rdi+80h], esi
0x18000d889  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d890  jmp     short loc_18000D897
0x18000d892  mov     ebx, 80070057h
0x18000d897  cmp     rcx, r14
0x18000d89a  jz      short loc_18000D8BA
0x18000d89c  test    byte ptr [rcx+1Ch], 20h
0x18000d8a0  jz      short loc_18000D8BA
0x18000d8a2  mov     rcx, [rcx+10h]
0x18000d8a6  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000d8ad  mov     edx, 97h
0x18000d8b2  mov     r9d, ebx
0x18000d8b5  call    WPP_SF_d
0x18000d8ba  mov     eax, ebx
0x18000d8bc  add     rsp, 20h
0x18000d8c0  pop     r14
0x18000d8c2  pop     rdi
0x18000d8c3  pop     rsi
0x18000d8c4  pop     rbp
0x18000d8c5  pop     rbx
0x18000d8c6  retn
```
