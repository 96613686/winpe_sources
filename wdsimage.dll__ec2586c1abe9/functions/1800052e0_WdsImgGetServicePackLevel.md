# WdsImgGetServicePackLevel

- ea: `0x1800052e0`
- end: `0x180005373`
- name: `WdsImgGetServicePackLevel`
- size: `147`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180003c68`
- `0x1800052e0`
- `0x1800083b4`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgGetServicePackLevel(void *a1, _QWORD *a2)
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
      v9 = (_WORD *)*((_QWORD *)v11 + 34);
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
0x1800052e0  mov     r11, rsp
0x1800052e3  mov     [r11+10h], rbx
0x1800052e7  mov     [r11+18h], rsi
0x1800052eb  push    rdi
0x1800052ec  sub     rsp, 20h
0x1800052f0  xor     esi, esi
0x1800052f2  mov     rax, rcx
0x1800052f5  mov     ecx, esi
0x1800052f7  mov     rdi, rdx
0x1800052fa  mov     [r11+8], rcx
0x1800052fe  test    rax, rax
0x180005301  jz      short loc_18000534A
0x180005303  test    rdx, rdx
0x180005306  jz      short loc_18000534A
0x180005308  lea     rdx, [r11+8]; struct CImage **
0x18000530c  mov     rcx, rax; void *
0x18000530f  call    ?GetImageFromHandle@CEnumImages@@SAJPEAXPEAPEAVCImage@@@Z; CEnumImages::GetImageFromHandle(void *,CImage * *)
0x180005314  lea     r9d, [rsi+6Bh]
0x180005318  mov     ecx, eax
0x18000531a  mov     ebx, eax
0x18000531c  call    ElValidateHr_0
0x180005321  mov     rcx, [rsp+28h+arg_0]
0x180005326  test    eax, eax
0x180005328  js      short loc_18000534F
0x18000532a  mov     rax, [rcx+110h]
0x180005331  test    rax, rax
0x180005334  jz      short loc_180005340
0x180005336  cmp     [rax], si
0x180005339  jz      short loc_180005340
0x18000533b  mov     [rdi], rax
0x18000533e  jmp     short loc_18000534F
0x180005340  mov     [rdi], rsi
0x180005343  mov     ebx, 0C1020201h
0x180005348  jmp     short loc_18000534F
0x18000534a  mov     ebx, 80070057h
0x18000534f  test    rcx, rcx
0x180005352  jz      short loc_180005360
0x180005354  mov     rax, [rcx]
0x180005357  mov     rax, [rax+8]
0x18000535b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005360  mov     rsi, [rsp+28h+arg_10]
0x180005365  mov     eax, ebx
0x180005367  mov     rbx, [rsp+28h+arg_8]
0x18000536c  add     rsp, 20h
0x180005370  pop     rdi
0x180005371  retn
```
