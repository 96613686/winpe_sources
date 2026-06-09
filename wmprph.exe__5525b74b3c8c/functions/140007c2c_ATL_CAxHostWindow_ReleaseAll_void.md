# ATL::CAxHostWindow::ReleaseAll(void)

- ea: `0x140007c2c`
- end: `0x140007ec2`
- name: `?ReleaseAll@CAxHostWindow@ATL@@QEAAXXZ`
- size: `662`
- prototype: `void __fastcall(ATL::CAxHostWindow *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002f70`
- `0x140003470`
- `0x140006cf0`
- `0x140007ba0`
- `0x140009710`

## callees

- `0x140007c2c`
- `0x14000f010`

## pseudocode

```c
void __fastcall ATL::CAxHostWindow::ReleaseAll(ATL::CAxHostWindow *this)
{
  int v1; // eax
  __int64 v3; // rcx
  unsigned int v4; // edi
  int (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall **v6)(_QWORD, GUID *, __int64 *); // rax
  __int64 v7; // rcx
  void (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+40h] [rbp+10h] BYREF
  __int64 v16; // [rsp+48h] [rbp+18h] BYREF

  v1 = *((_DWORD *)this + 62);
  if ( (v1 & 0x40) == 0 )
  {
    *((_DWORD *)this + 62) = v1 | 0x40;
    v3 = *((_QWORD *)this + 24);
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v3 + 56LL))(v3, 1, 0);
    v4 = *((_DWORD *)this + 61);
    if ( v4 != -842150451 )
    {
      v5 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 20);
      if ( v5 )
      {
        v6 = *v5;
        v16 = 0;
        v15 = 0;
        if ( (*v6)(v5, &IID_IConnectionPointContainer, &v16) >= 0
          && (*(int (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v16 + 32LL))(v16, (char *)this + 224, &v15) >= 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 48LL))(v15, v4);
        }
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      *((_DWORD *)this + 61) = -842150451;
    }
    v7 = *((_QWORD *)this + 21);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 160LL))(v7, *((unsigned int *)this + 63));
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 21) + 48LL))(*((_QWORD *)this + 21), 1);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 21) + 24LL))(*((_QWORD *)this + 21), 0);
    }
    v8 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 20);
    if ( v8 )
    {
      v15 = 0;
      (**v8)(v8, &IID_IObjectWithSite, &v15);
      if ( v15 )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, 0);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    v9 = *((_QWORD *)this + 24);
    if ( v9 )
    {
      *((_QWORD *)this + 24) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    *((_DWORD *)this + 60) = 0;
    v10 = *((_QWORD *)this + 25);
    if ( v10 )
    {
      *((_QWORD *)this + 25) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = *((_QWORD *)this + 21);
    if ( v11 )
    {
      *((_QWORD *)this + 21) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = *((_QWORD *)this + 20);
    if ( v12 )
    {
      *((_QWORD *)this + 20) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = *((_QWORD *)this + 23);
    if ( v13 )
    {
      *((_QWORD *)this + 23) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = *((_QWORD *)this + 22);
    if ( v14 )
    {
      *((_QWORD *)this + 22) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    *((_DWORD *)this + 62) &= 0xFFFFFFA4;
  }
}

```

## disassembly

```asm
0x140007c2c  mov     [rsp-8+arg_10], rbx
0x140007c31  mov     [rsp-8+arg_18], rdi
0x140007c36  push    rbp
0x140007c37  mov     rbp, rsp
0x140007c3a  sub     rsp, 30h
0x140007c3e  mov     eax, [rcx+0F8h]
0x140007c44  mov     rbx, rcx
0x140007c47  test    al, 40h
0x140007c49  jnz     loc_140007EB2
0x140007c4f  or      eax, 40h
0x140007c52  mov     [rcx+0F8h], eax
0x140007c58  mov     rcx, [rcx+0C0h]
0x140007c5f  test    rcx, rcx
0x140007c62  jz      short loc_140007C7A
0x140007c64  mov     rax, [rcx]
0x140007c67  xor     r9d, r9d
0x140007c6a  xor     r8d, r8d
0x140007c6d  mov     rax, [rax+38h]
0x140007c71  lea     edx, [r9+1]
0x140007c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c7a  mov     edi, [rbx+0F4h]
0x140007c80  cmp     edi, 0CDCDCDCDh
0x140007c86  jz      loc_140007D2B
0x140007c8c  mov     rcx, [rbx+0A0h]
0x140007c93  test    rcx, rcx
0x140007c96  jz      loc_140007D21
0x140007c9c  mov     rax, [rcx]
0x140007c9f  lea     r8, [rbp+arg_8]
0x140007ca3  lea     rdx, IID_IConnectionPointContainer
0x140007caa  mov     [rbp+arg_8], 0
0x140007cb2  mov     [rbp+arg_0], 0
0x140007cba  mov     rax, [rax]
0x140007cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cc2  test    eax, eax
0x140007cc4  js      short loc_140007CF7
0x140007cc6  mov     rcx, [rbp+arg_8]
0x140007cca  lea     rdx, [rbx+0E0h]
0x140007cd1  lea     r8, [rbp+arg_0]
0x140007cd5  mov     rax, [rcx]
0x140007cd8  mov     rax, [rax+20h]
0x140007cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ce1  test    eax, eax
0x140007ce3  js      short loc_140007CF7
0x140007ce5  mov     rcx, [rbp+arg_0]
0x140007ce9  mov     edx, edi
0x140007ceb  mov     rax, [rcx]
0x140007cee  mov     rax, [rax+30h]
0x140007cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cf7  mov     rcx, [rbp+arg_0]
0x140007cfb  test    rcx, rcx
0x140007cfe  jz      short loc_140007D0C
0x140007d00  mov     rax, [rcx]
0x140007d03  mov     rax, [rax+10h]
0x140007d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d0c  mov     rcx, [rbp+arg_8]
0x140007d10  test    rcx, rcx
0x140007d13  jz      short loc_140007D21
0x140007d15  mov     rax, [rcx]
0x140007d18  mov     rax, [rax+10h]
0x140007d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d21  mov     dword ptr [rbx+0F4h], 0CDCDCDCDh
0x140007d2b  mov     rcx, [rbx+0A8h]
0x140007d32  test    rcx, rcx
0x140007d35  jz      short loc_140007D79
0x140007d37  mov     rax, [rcx]
0x140007d3a  mov     edx, [rbx+0FCh]
0x140007d40  mov     rax, [rax+0A0h]
0x140007d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d4c  mov     rcx, [rbx+0A8h]
0x140007d53  mov     edx, 1
0x140007d58  mov     rax, [rcx]
0x140007d5b  mov     rax, [rax+30h]
0x140007d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d64  mov     rcx, [rbx+0A8h]
0x140007d6b  xor     edx, edx
0x140007d6d  mov     rax, [rcx]
0x140007d70  mov     rax, [rax+18h]
0x140007d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d79  mov     rcx, [rbx+0A0h]
0x140007d80  test    rcx, rcx
0x140007d83  jz      short loc_140007DCF
0x140007d85  mov     [rbp+arg_0], 0
0x140007d8d  lea     r8, [rbp+arg_0]
0x140007d91  mov     rax, [rcx]
0x140007d94  lea     rdx, IID_IObjectWithSite
0x140007d9b  mov     rax, [rax]
0x140007d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007da3  mov     rcx, [rbp+arg_0]
0x140007da7  test    rcx, rcx
0x140007daa  jz      short loc_140007DCF
0x140007dac  mov     rax, [rcx]
0x140007daf  xor     edx, edx
0x140007db1  mov     rax, [rax+18h]
0x140007db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007dba  mov     rcx, [rbp+arg_0]
0x140007dbe  test    rcx, rcx
0x140007dc1  jz      short loc_140007DCF
0x140007dc3  mov     rax, [rcx]
0x140007dc6  mov     rax, [rax+10h]
0x140007dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007dcf  mov     rcx, [rbx+0C0h]
0x140007dd6  test    rcx, rcx
0x140007dd9  jz      short loc_140007DF2
0x140007ddb  mov     qword ptr [rbx+0C0h], 0
0x140007de6  mov     rax, [rcx]
0x140007de9  mov     rax, [rax+10h]
0x140007ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007df2  mov     dword ptr [rbx+0F0h], 0
0x140007dfc  mov     rcx, [rbx+0C8h]
0x140007e03  test    rcx, rcx
0x140007e06  jz      short loc_140007E1F
0x140007e08  mov     qword ptr [rbx+0C8h], 0
0x140007e13  mov     rax, [rcx]
0x140007e16  mov     rax, [rax+10h]
0x140007e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e1f  mov     rcx, [rbx+0A8h]
0x140007e26  test    rcx, rcx
0x140007e29  jz      short loc_140007E42
0x140007e2b  mov     qword ptr [rbx+0A8h], 0
0x140007e36  mov     rax, [rcx]
0x140007e39  mov     rax, [rax+10h]
0x140007e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e42  mov     rcx, [rbx+0A0h]
0x140007e49  test    rcx, rcx
0x140007e4c  jz      short loc_140007E65
0x140007e4e  mov     qword ptr [rbx+0A0h], 0
0x140007e59  mov     rax, [rcx]
0x140007e5c  mov     rax, [rax+10h]
0x140007e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e65  mov     rcx, [rbx+0B8h]
0x140007e6c  test    rcx, rcx
0x140007e6f  jz      short loc_140007E88
0x140007e71  mov     qword ptr [rbx+0B8h], 0
0x140007e7c  mov     rax, [rcx]
0x140007e7f  mov     rax, [rax+10h]
0x140007e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e88  mov     rcx, [rbx+0B0h]
0x140007e8f  test    rcx, rcx
0x140007e92  jz      short loc_140007EAB
0x140007e94  mov     qword ptr [rbx+0B0h], 0
0x140007e9f  mov     rax, [rcx]
0x140007ea2  mov     rax, [rax+10h]
0x140007ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007eab  and     dword ptr [rbx+0F8h], 0FFFFFFA4h
0x140007eb2  mov     rbx, [rsp+30h+arg_10]
0x140007eb7  mov     rdi, [rsp+30h+arg_18]
0x140007ebc  add     rsp, 30h
0x140007ec0  pop     rbp
0x140007ec1  retn
```
