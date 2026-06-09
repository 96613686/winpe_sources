# CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)

- ea: `0x180004a78`
- end: `0x180004b0a`
- name: `?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z`
- size: `146`
- prototype: `int __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000610c`
- `0x18001de8c`
- `0x1800200c0`
- `0x180020c6c`
- `0x180021bc4`
- `0x180023310`
- `0x18003a05c`

## callees

- `0x180002138`
- `0x1800049e0`
- `0x180004a78`
- `0x180007604`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004aa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004aa3`

## pseudocode

```c
int __fastcall CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom(__int64 a1, const unsigned __int16 *a2)
{
  __int64 v2; // rbx
  unsigned __int16 *v5; // rax
  int result; // eax
  int pExceptionObject; // [rsp+50h] [rbp+8h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(a1);
  v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * v2 + 2);
  *(_QWORD *)(a1 + 8) = v5;
  if ( !v5 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  result = StringCchCopyW(v5, v2 + 1, a2);
  if ( result < 0 )
  {
    CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(a1);
    pExceptionObject = -2147418113;
    throw (long *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180004a78  push    rbx
0x180004a7a  push    rbp
0x180004a7b  push    rsi
0x180004a7c  push    rdi
0x180004a7d  sub     rsp, 28h
0x180004a81  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004a85  mov     rsi, rdx
0x180004a88  xor     ebp, ebp
0x180004a8a  mov     rdi, rcx
0x180004a8d  inc     rbx
0x180004a90  cmp     [rdx+rbx*2], bp
0x180004a94  jnz     short loc_180004A8D
0x180004a96  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x180004a9b  lea     rcx, ds:2[rbx*2]; cb
0x180004aa3  call    cs:__imp_CoTaskMemAlloc
0x180004aa9  mov     [rdi+8], rax
0x180004aad  test    rax, rax
0x180004ab0  jnz     short loc_180004ACC
0x180004ab2  lea     rdx, _TI1J; pThrowInfo
0x180004ab9  mov     [rsp+48h+pExceptionObject], 8007000Eh
0x180004ac1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180004ac6  call    _CxxThrowException_0
0x180004acc  lea     rdx, [rbx+1]; unsigned __int64
0x180004ad0  mov     r8, rsi; unsigned __int16 *
0x180004ad3  mov     rcx, rax; unsigned __int16 *
0x180004ad6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004adb  test    eax, eax
0x180004add  jns     short loc_180004B01
0x180004adf  mov     rcx, rdi
0x180004ae2  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x180004ae7  lea     rdx, _TI1J; pThrowInfo
0x180004aee  mov     [rsp+48h+pExceptionObject], 8000FFFFh
0x180004af6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180004afb  call    _CxxThrowException_0
0x180004b01  add     rsp, 28h
0x180004b05  pop     rdi
0x180004b06  pop     rsi
0x180004b07  pop     rbp
0x180004b08  pop     rbx
0x180004b09  retn
```
