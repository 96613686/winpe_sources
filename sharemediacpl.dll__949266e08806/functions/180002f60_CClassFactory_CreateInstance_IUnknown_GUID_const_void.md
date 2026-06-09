# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002f60`
- end: `0x180003070`
- name: `?CreateInstance@CClassFactory@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `272`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002f60`
- `0x180003860`
- `0x180003888`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v9; // ebx
  __int64 (__fastcall *v10)(struct IUnknown *, __int64 *, CClassFactory *); // rax
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_6dd76389fe1d31293452cff392e3d361_Traceguids);
  *a4 = 0;
  if ( !a2 )
  {
LABEL_10:
    v10 = (__int64 (__fastcall *)(struct IUnknown *, __int64 *, CClassFactory *))*((_QWORD *)this + 2);
    v11 = 0;
    v9 = v10(a2, &v11, this);
    if ( v9 >= 0 )
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v11)(v11, a3, a4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_12;
  }
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    if ( (*((_BYTE *)this + 48) & 1) == 0 )
      return 2147746064LL;
    goto LABEL_10;
  }
  v9 = -2147221232;
LABEL_12:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      &WPP_6dd76389fe1d31293452cff392e3d361_Traceguids,
      (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002f60  mov     [rsp+arg_0], rbx
0x180002f65  mov     [rsp+arg_10], rbp
0x180002f6a  push    rsi
0x180002f6b  push    rdi
0x180002f6c  push    r14
0x180002f6e  sub     rsp, 20h
0x180002f72  mov     r14, r9
0x180002f75  mov     rdi, r8
0x180002f78  mov     rsi, rdx
0x180002f7b  mov     rbx, rcx
0x180002f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f85  lea     rbp, WPP_GLOBAL_Control
0x180002f8c  cmp     rcx, rbp
0x180002f8f  jz      short loc_180002FAC
0x180002f91  test    byte ptr [rcx+1Ch], 20h
0x180002f95  jz      short loc_180002FAC
0x180002f97  mov     rcx, [rcx+10h]
0x180002f9b  lea     r8, WPP_6dd76389fe1d31293452cff392e3d361_Traceguids
0x180002fa2  mov     edx, 1Eh
0x180002fa7  call    WPP_SF_
0x180002fac  mov     qword ptr [r14], 0
0x180002fb3  test    rsi, rsi
0x180002fb6  jz      short loc_180002FE5
0x180002fb8  mov     rax, [rdi]
0x180002fbb  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002fc2  jnz     short loc_180002FDE
0x180002fc4  mov     rax, [rdi+8]
0x180002fc8  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002fcf  jnz     short loc_180002FDE
0x180002fd1  test    byte ptr [rbx+30h], 1
0x180002fd5  jnz     short loc_180002FE5
0x180002fd7  mov     eax, 80040110h
0x180002fdc  jmp     short loc_18000305D
0x180002fde  mov     ebx, 80040110h
0x180002fe3  jmp     short loc_180003031
0x180002fe5  mov     rax, [rbx+10h]
0x180002fe9  lea     rdx, [rsp+38h+arg_8]
0x180002fee  mov     r8, rbx
0x180002ff1  mov     [rsp+38h+arg_8], 0
0x180002ffa  mov     rcx, rsi
0x180002ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003002  mov     ebx, eax
0x180003004  test    eax, eax
0x180003006  js      short loc_180003031
0x180003008  mov     rcx, [rsp+38h+arg_8]
0x18000300d  mov     r8, r14
0x180003010  mov     rdx, rdi
0x180003013  mov     rax, [rcx]
0x180003016  mov     rax, [rax]
0x180003019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301e  mov     rcx, [rsp+38h+arg_8]
0x180003023  mov     ebx, eax
0x180003025  mov     rax, [rcx]
0x180003028  mov     rax, [rax+10h]
0x18000302c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003031  mov     rcx, cs:WPP_GLOBAL_Control
0x180003038  cmp     rcx, rbp
0x18000303b  jz      short loc_18000305B
0x18000303d  test    byte ptr [rcx+1Ch], 20h
0x180003041  jz      short loc_18000305B
0x180003043  mov     rcx, [rcx+10h]
0x180003047  lea     r8, WPP_6dd76389fe1d31293452cff392e3d361_Traceguids
0x18000304e  mov     edx, 1Fh
0x180003053  mov     r9d, ebx
0x180003056  call    WPP_SF_d
0x18000305b  mov     eax, ebx
0x18000305d  mov     rbx, [rsp+38h+arg_0]
0x180003062  mov     rbp, [rsp+38h+arg_10]
0x180003067  add     rsp, 20h
0x18000306b  pop     r14
0x18000306d  pop     rdi
0x18000306e  pop     rsi
0x18000306f  retn
```
