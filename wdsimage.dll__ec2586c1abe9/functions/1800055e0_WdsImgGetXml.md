# WdsImgGetXml

- ea: `0x1800055e0`
- end: `0x180005673`
- name: `WdsImgGetXml`
- size: `147`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003c68`
- `0x1800055e0`
- `0x1800083b4`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgGetXml(void *a1, _QWORD *a2)
{
  struct CImage *v3; // rcx
  __int64 ImageFromHandle; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  _WORD *v9; // rax
  struct CImage *v11; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  v11 = 0;
  if ( a1 && a2 )
  {
    ImageFromHandle = (unsigned int)CEnumImages::GetImageFromHandle(a1, &v11);
    v8 = ElValidateHr_0(ImageFromHandle, v6, v7, 107);
    v3 = v11;
    if ( v8 >= 0 )
    {
      v9 = (_WORD *)*((_QWORD *)v11 + 38);
      if ( v9 && *v9 )
      {
        *a2 = v9;
      }
      else
      {
        *a2 = 0;
        LODWORD(ImageFromHandle) = -1056833023;
      }
    }
  }
  else
  {
    LODWORD(ImageFromHandle) = -2147024809;
  }
  if ( v3 )
    (*(void (__fastcall **)(struct CImage *))(*(_QWORD *)v3 + 8LL))(v3);
  return (unsigned int)ImageFromHandle;
}

```

## disassembly

```asm
0x1800055e0  mov     r11, rsp
0x1800055e3  mov     [r11+10h], rbx
0x1800055e7  mov     [r11+18h], rsi
0x1800055eb  push    rdi
0x1800055ec  sub     rsp, 20h
0x1800055f0  xor     esi, esi
0x1800055f2  mov     rax, rcx
0x1800055f5  mov     ecx, esi
0x1800055f7  mov     rdi, rdx
0x1800055fa  mov     [r11+8], rcx
0x1800055fe  test    rax, rax
0x180005601  jz      short loc_18000564A
0x180005603  test    rdx, rdx
0x180005606  jz      short loc_18000564A
0x180005608  lea     rdx, [r11+8]; struct CImage **
0x18000560c  mov     rcx, rax; void *
0x18000560f  call    ?GetImageFromHandle@CEnumImages@@SAJPEAXPEAPEAVCImage@@@Z; CEnumImages::GetImageFromHandle(void *,CImage * *)
0x180005614  lea     r9d, [rsi+6Bh]
0x180005618  mov     ecx, eax
0x18000561a  mov     ebx, eax
0x18000561c  call    ElValidateHr_0
0x180005621  mov     rcx, [rsp+28h+arg_0]
0x180005626  test    eax, eax
0x180005628  js      short loc_18000564F
0x18000562a  mov     rax, [rcx+130h]
0x180005631  test    rax, rax
0x180005634  jz      short loc_180005640
0x180005636  cmp     [rax], si
0x180005639  jz      short loc_180005640
0x18000563b  mov     [rdi], rax
0x18000563e  jmp     short loc_18000564F
0x180005640  mov     [rdi], rsi
0x180005643  mov     ebx, 0C1020201h
0x180005648  jmp     short loc_18000564F
0x18000564a  mov     ebx, 80070057h
0x18000564f  test    rcx, rcx
0x180005652  jz      short loc_180005660
0x180005654  mov     rax, [rcx]
0x180005657  mov     rax, [rax+8]
0x18000565b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005660  mov     rsi, [rsp+28h+arg_10]
0x180005665  mov     eax, ebx
0x180005667  mov     rbx, [rsp+28h+arg_8]
0x18000566c  add     rsp, 20h
0x180005670  pop     rdi
0x180005671  retn
```
