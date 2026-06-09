# CDVRASFMMStream::CreateHeaderObject(CASFLonghandObject * *,CASFArchive &)

- ea: `0x180002660`
- end: `0x180002709`
- name: `?CreateHeaderObject@CDVRASFMMStream@@UEAAJPEAPEAVCASFLonghandObject@@AEAVCASFArchive@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(CDVRASFMMStream *__hidden this, struct CASFLonghandObject **, struct CASFArchive *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002660`
- `0x180012080`
- `0x18002a064`

## pseudocode

```c
__int64 __fastcall CDVRASFMMStream::CreateHeaderObject(
        CDVRASFMMStream *this,
        struct CASFLonghandObject **a2,
        struct CASFArchive *a3)
{
  int HeaderObject; // edi
  struct CASFLonghandObject *v7; // rbp
  _OWORD Buf1[3]; // [rsp+20h] [rbp-38h] BYREF

  HeaderObject = CASFMMStream::CreateHeaderObject(this, a2, a3);
  if ( HeaderObject >= 0 )
  {
    v7 = *a2;
    Buf1[0] = *((_OWORD *)*a2 + 1);
    if ( !memcmp_0(Buf1, &CLSID_CAsfPropertiesObjectV0, 0x10u)
      || !memcmp_0(Buf1, &CLSID_CAsfPropertiesObjectV1, 0x10u)
      || !memcmp_0(Buf1, &CLSID_CAsfPropertiesObjectV2, 0x10u) )
    {
      HeaderObject = 0;
      *((_QWORD *)this + 171) = *((_QWORD *)a3 + 1) - *((_QWORD *)v7 + 4) - *(_QWORD *)a3;
    }
    *((_QWORD *)this + 172) = *((_QWORD *)a3 + 1) - *(_QWORD *)a3;
  }
  return (unsigned int)HeaderObject;
}

```

## disassembly

```asm
0x180002660  push    rbx
0x180002662  push    rbp
0x180002663  push    rsi
0x180002664  push    rdi
0x180002665  push    r14
0x180002667  sub     rsp, 30h
0x18000266b  mov     rbx, r8
0x18000266e  mov     r14, rdx
0x180002671  mov     rsi, rcx
0x180002674  call    ?CreateHeaderObject@CASFMMStream@@MEAAJPEAPEAVCASFLonghandObject@@AEAVCASFArchive@@@Z; CASFMMStream::CreateHeaderObject(CASFLonghandObject * *,CASFArchive &)
0x180002679  mov     edi, eax
0x18000267b  test    eax, eax
0x18000267d  js      short loc_1800026FC
0x18000267f  mov     rbp, [r14]
0x180002682  lea     rdx, CLSID_CAsfPropertiesObjectV0; Buf2
0x180002689  mov     r14d, 10h
0x18000268f  lea     rcx, [rsp+58h+Buf1]; Buf1
0x180002694  mov     r8d, r14d; Size
0x180002697  movups  xmm0, xmmword ptr [rbp+10h]
0x18000269b  movdqu  [rsp+58h+Buf1], xmm0
0x1800026a1  call    memcmp_0
0x1800026a6  test    eax, eax
0x1800026a8  jz      short loc_1800026DA
0x1800026aa  mov     r8d, r14d; Size
0x1800026ad  lea     rdx, CLSID_CAsfPropertiesObjectV1; Buf2
0x1800026b4  lea     rcx, [rsp+58h+Buf1]; Buf1
0x1800026b9  call    memcmp_0
0x1800026be  test    eax, eax
0x1800026c0  jz      short loc_1800026DA
0x1800026c2  mov     r8d, r14d; Size
0x1800026c5  lea     rdx, CLSID_CAsfPropertiesObjectV2; Buf2
0x1800026cc  lea     rcx, [rsp+58h+Buf1]; Buf1
0x1800026d1  call    memcmp_0
0x1800026d6  test    eax, eax
0x1800026d8  jnz     short loc_1800026EE
0x1800026da  mov     rax, [rbx+8]
0x1800026de  xor     edi, edi
0x1800026e0  sub     rax, [rbp+20h]
0x1800026e4  sub     rax, [rbx]
0x1800026e7  mov     [rsi+558h], rax
0x1800026ee  mov     rax, [rbx+8]
0x1800026f2  sub     rax, [rbx]
0x1800026f5  mov     [rsi+560h], rax
0x1800026fc  mov     eax, edi
0x1800026fe  add     rsp, 30h
0x180002702  pop     r14
0x180002704  pop     rdi
0x180002705  pop     rsi
0x180002706  pop     rbp
0x180002707  pop     rbx
0x180002708  retn
```
