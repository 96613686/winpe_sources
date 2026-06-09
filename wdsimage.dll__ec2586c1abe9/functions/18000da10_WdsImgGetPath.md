# WdsImgGetPath

- ea: `0x18000da10`
- end: `0x18000db40`
- name: `WdsImgGetPath`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000db50`

## callees

- `0x180007720`
- `0x18000d780`
- `0x18000da10`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgGetPath(__int64 a1, _QWORD *a2, __int64 a3)
{
  struct CImageGroup *v3; // rdi
  __int64 v4; // rsi
  _QWORD *v5; // r14
  __int64 v8; // rdx
  void (__fastcall ***v9)(_QWORD); // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  struct CImageGroup *v15; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  LODWORD(v4) = 0;
  v5 = 0;
  v15 = 0;
  if ( a1 && a2 )
  {
    switch ( *(_DWORD *)(a1 + 16) )
    {
      case 1:
        v10 = *(_QWORD *)(a1 + 24);
        goto LABEL_20;
      case 2:
      case 3:
        v10 = *(_QWORD *)(a1 + 32);
        v3 = (struct CImageGroup *)a1;
        goto LABEL_20;
      case 4:
        v10 = *(_QWORD *)(a1 + 88);
        v5 = (_QWORD *)a1;
        goto LABEL_20;
    }
    v8 = (unsigned int)(*(_DWORD *)(a1 + 16) - 5);
    if ( *(_DWORD *)(a1 + 16) != 5 )
    {
      if ( *(_DWORD *)(a1 + 16) != 6 )
      {
        LODWORD(v4) = -1056833019;
        return (unsigned int)v4;
      }
      v9 = *(void (__fastcall ****)(_QWORD))(a1 + 64);
      if ( v9 )
      {
        v5 = v9;
        (**v9)(v9);
      }
      else
      {
        LODWORD(v4) = -1056833013;
      }
      if ( (int)ElValidateHr_6((unsigned int)v4, v8, a3, 280) < 0 )
        goto LABEL_21;
      v10 = v5[11];
LABEL_20:
      *a2 = v10;
LABEL_21:
      if ( v5 && v5 != (_QWORD *)a1 )
        (*(void (__fastcall **)(_QWORD *))(*v5 + 8LL))(v5);
      goto LABEL_25;
    }
    v4 = (unsigned int)CEnumImageGroups::GetAt((CEnumImageGroups *)a1, &v15);
    v13 = ElValidateHr_6(v4, v11, v12, 289);
    v3 = v15;
    if ( v13 >= 0 )
    {
      v10 = *((_QWORD *)v15 + 4);
      goto LABEL_20;
    }
  }
  else
  {
    LODWORD(v4) = -2147024809;
  }
LABEL_25:
  if ( v3 && v3 != (struct CImageGroup *)a1 )
    (*(void (__fastcall **)(struct CImageGroup *))(*(_QWORD *)v3 + 8LL))(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000da10  mov     [rsp+arg_8], rbx
0x18000da15  mov     [rsp+arg_10], rsi
0x18000da1a  push    rdi
0x18000da1b  push    r14
0x18000da1d  push    r15
0x18000da1f  sub     rsp, 20h
0x18000da23  xor     edi, edi
0x18000da25  xor     esi, esi
0x18000da27  xor     r14d, r14d
0x18000da2a  mov     [rsp+38h+arg_0], rdi
0x18000da2f  mov     r15, rdx
0x18000da32  mov     rbx, rcx
0x18000da35  test    rcx, rcx
0x18000da38  jz      loc_18000DB0B
0x18000da3e  test    rdx, rdx
0x18000da41  jz      loc_18000DB0B
0x18000da47  mov     edx, [rcx+10h]
0x18000da4a  sub     edx, 1
0x18000da4d  jz      loc_18000DAE9
0x18000da53  sub     edx, 1
0x18000da56  jz      loc_18000DAE0
0x18000da5c  sub     edx, 1
0x18000da5f  jz      short loc_18000DAE0
0x18000da61  sub     edx, 1
0x18000da64  jz      short loc_18000DAD7
0x18000da66  sub     edx, 1
0x18000da69  jz      short loc_18000DAAF
0x18000da6b  cmp     edx, 1
0x18000da6e  jz      short loc_18000DA7A
0x18000da70  mov     esi, 0C1020205h
0x18000da75  jmp     loc_18000DB29
0x18000da7a  mov     rcx, [rcx+40h]
0x18000da7e  test    rcx, rcx
0x18000da81  jnz     short loc_18000DA8A
0x18000da83  mov     esi, 0C102020Bh
0x18000da88  jmp     short loc_18000DA98
0x18000da8a  mov     rax, [rcx]
0x18000da8d  mov     r14, rcx
0x18000da90  mov     rax, [rax]
0x18000da93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da98  mov     r9d, 118h
0x18000da9e  mov     ecx, esi
0x18000daa0  call    ElValidateHr_6
0x18000daa5  test    eax, eax
0x18000daa7  js      short loc_18000DAF0
0x18000daa9  mov     rax, [r14+58h]
0x18000daad  jmp     short loc_18000DAED
0x18000daaf  lea     rdx, [rsp+38h+arg_0]; struct CImageGroup **
0x18000dab4  call    ?GetAt@CEnumImageGroups@@QEAAJPEAPEAVCImageGroup@@@Z; CEnumImageGroups::GetAt(CImageGroup * *)
0x18000dab9  mov     r9d, 121h
0x18000dabf  mov     ecx, eax
0x18000dac1  mov     esi, eax
0x18000dac3  call    ElValidateHr_6
0x18000dac8  mov     rdi, [rsp+38h+arg_0]
0x18000dacd  test    eax, eax
0x18000dacf  js      short loc_18000DB10
0x18000dad1  mov     rax, [rdi+20h]
0x18000dad5  jmp     short loc_18000DAED
0x18000dad7  mov     rax, [rcx+58h]
0x18000dadb  mov     r14, rbx
0x18000dade  jmp     short loc_18000DAED
0x18000dae0  mov     rax, [rcx+20h]
0x18000dae4  mov     rdi, rbx
0x18000dae7  jmp     short loc_18000DAED
0x18000dae9  mov     rax, [rcx+18h]
0x18000daed  mov     [r15], rax
0x18000daf0  test    r14, r14
0x18000daf3  jz      short loc_18000DB10
0x18000daf5  cmp     r14, rbx
0x18000daf8  jz      short loc_18000DB10
0x18000dafa  mov     rax, [r14]
0x18000dafd  mov     rcx, r14
0x18000db00  mov     rax, [rax+8]
0x18000db04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db09  jmp     short loc_18000DB10
0x18000db0b  mov     esi, 80070057h
0x18000db10  test    rdi, rdi
0x18000db13  jz      short loc_18000DB29
0x18000db15  cmp     rdi, rbx
0x18000db18  jz      short loc_18000DB29
0x18000db1a  mov     rax, [rdi]
0x18000db1d  mov     rcx, rdi
0x18000db20  mov     rax, [rax+8]
0x18000db24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db29  mov     rbx, [rsp+38h+arg_8]
0x18000db2e  mov     eax, esi
0x18000db30  mov     rsi, [rsp+38h+arg_10]
0x18000db35  add     rsp, 20h
0x18000db39  pop     r15
0x18000db3b  pop     r14
0x18000db3d  pop     rdi
0x18000db3e  retn
```
