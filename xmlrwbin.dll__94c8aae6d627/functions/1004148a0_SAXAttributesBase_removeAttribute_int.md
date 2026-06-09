# SAXAttributesBase::removeAttribute(int)

- ea: `0x1004148a0`
- end: `0x10041497f`
- name: `?removeAttribute@SAXAttributesBase@@UEAAJH@Z`
- size: `223`
- prototype: `__int64 __fastcall(SAXAttributesBase *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x100413bb0`
- `0x1004148a0`

## pseudocode

```c
__int64 __fastcall SAXAttributesBase::removeAttribute(SAXAttributesBase *this, int a2)
{
  unsigned int v3; // esi
  int v4; // eax
  int v5; // r14d
  unsigned int i; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax

  v3 = 0;
  if ( a2 < 0 )
    return (unsigned int)-2147024809;
  v4 = *((_DWORD *)this + 12);
  if ( a2 >= v4 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    if ( a2 < v4 - 1 )
    {
      v5 = 5 * a2;
      for ( i = 5 * a2; i < *((_DWORD *)this + 9); ++i )
      {
        if ( i < v5 + 5 )
        {
          DataVal::free((DataVal *)(*((_QWORD *)this + 5) + 32LL * i), *((struct IMalloc **)this + 3));
          --*((_DWORD *)this + 9);
        }
        v7 = *((_QWORD *)this + 5);
        v8 = 32LL * (i + 5);
        v9 = 32LL * i;
        *(_OWORD *)(v9 + v7) = *(_OWORD *)(v8 + v7);
        *(_OWORD *)(v9 + v7 + 16) = *(_OWORD *)(v8 + v7 + 16);
      }
      while ( i < *((_DWORD *)this + 9) + 5 )
      {
        v10 = *((_QWORD *)this + 5) + 32LL * i;
        *(_QWORD *)(v10 + 8) = 0;
        *(_DWORD *)(v10 + 16) = 0;
        *(_QWORD *)(v10 + 24) = 0;
        ++i;
      }
    }
    --*((_DWORD *)this + 12);
  }
  return v3;
}

```

## disassembly

```asm
0x1004148a0  mov     [rsp+arg_0], rbx
0x1004148a5  mov     [rsp+arg_8], rsi
0x1004148aa  mov     [rsp+arg_10], rdi
0x1004148af  push    r14
0x1004148b1  sub     rsp, 50h
0x1004148b5  mov     rdi, rcx
0x1004148b8  xor     esi, esi
0x1004148ba  test    edx, edx
0x1004148bc  js      loc_100414962
0x1004148c2  mov     eax, [rcx+30h]
0x1004148c5  cmp     edx, eax
0x1004148c7  jge     loc_100414962
0x1004148cd  dec     eax
0x1004148cf  cmp     edx, eax
0x1004148d1  jge     loc_100414957
0x1004148d7  lea     r14d, [rdx+rdx*4]
0x1004148db  mov     ebx, r14d
0x1004148de  mov     [rsp+58h+var_34], ebx
0x1004148e2  cmp     ebx, [rdi+24h]
0x1004148e5  jnb     short loc_100414930
0x1004148e7  lea     eax, [r14+5]
0x1004148eb  cmp     ebx, eax
0x1004148ed  jnb     short loc_100414905
0x1004148ef  mov     ecx, ebx
0x1004148f1  shl     rcx, 5
0x1004148f5  add     rcx, [rdi+28h]; this
0x1004148f9  mov     rdx, [rdi+18h]; struct IMalloc *
0x1004148fd  call    ?free@DataVal@@QEAAXPEAUIMalloc@@@Z; DataVal::free(IMalloc *)
0x100414902  dec     dword ptr [rdi+24h]
0x100414905  mov     rdx, [rdi+28h]
0x100414909  lea     ecx, [rbx+5]
0x10041490c  shl     rcx, 5
0x100414910  mov     eax, ebx
0x100414912  shl     rax, 5
0x100414916  movups  xmm0, xmmword ptr [rcx+rdx]
0x10041491a  movups  xmmword ptr [rax+rdx], xmm0
0x10041491e  movups  xmm1, xmmword ptr [rcx+rdx+10h]
0x100414923  movups  xmmword ptr [rax+rdx+10h], xmm1
0x100414928  inc     ebx
0x10041492a  jmp     short loc_1004148DE
0x100414930  mov     eax, [rdi+24h]
0x100414933  add     eax, 5
0x100414936  cmp     ebx, eax
0x100414938  jnb     short loc_100414957
0x10041493a  mov     eax, ebx
0x10041493c  shl     rax, 5
0x100414940  add     rax, [rdi+28h]
0x100414944  mov     [rax+8], rsi
0x100414948  mov     [rax+10h], esi
0x10041494b  mov     [rax+18h], rsi
0x10041494f  inc     ebx
0x100414951  mov     [rsp+58h+var_34], ebx
0x100414955  jmp     short loc_100414930
0x100414957  dec     dword ptr [rdi+30h]
0x10041495a  jmp     short loc_100414967
0x10041495c  mov     esi, [rsp+58h+var_38]
0x100414960  jmp     short loc_100414967
0x100414962  mov     esi, 80070057h
0x100414967  mov     eax, esi
0x100414969  mov     rbx, [rsp+58h+arg_0]
0x10041496e  mov     rsi, [rsp+58h+arg_8]
0x100414973  mov     rdi, [rsp+58h+arg_10]
0x100414978  add     rsp, 50h
0x10041497c  pop     r14
0x10041497e  retn
0x100424eb0  push    rbp
0x100424eb2  sub     rsp, 20h
0x100424eb6  mov     rbp, rdx
0x100424eb9  mov     [rbp+40h], rcx
0x100424ebd  mov     [rbp+38h], rcx
0x100424ec1  mov     rax, [rbp+38h]
0x100424ec5  mov     rcx, [rax]
0x100424ec8  mov     [rbp+30h], rcx
0x100424ecc  mov     rax, [rbp+30h]
0x100424ed0  mov     eax, [rax]
0x100424ed2  cmp     eax, 0C0000005h
0x100424ed7  jz      short loc_100424F09
0x100424ed9  add     eax, 1FFFFFFFh
0x100424ede  cmp     eax, 1
0x100424ee1  ja      short loc_100424EF9
0x100424ee3  mov     rax, [rbp+30h]
0x100424ee7  cmp     dword ptr [rax+18h], 1
0x100424eeb  jnz     short loc_100424EF9
0x100424eed  mov     rax, [rbp+30h]
0x100424ef1  mov     ecx, [rax+20h]
0x100424ef4  mov     [rbp+20h], ecx
0x100424ef7  jmp     short loc_100424F00
0x100424ef9  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424f00  mov     dword ptr [rbp+28h], 1
0x100424f07  jmp     short loc_100424F10
0x100424f09  mov     dword ptr [rbp+28h], 0
0x100424f10  mov     eax, [rbp+28h]
0x100424f13  add     rsp, 20h
0x100424f17  pop     rbp
0x100424f18  retn
```
