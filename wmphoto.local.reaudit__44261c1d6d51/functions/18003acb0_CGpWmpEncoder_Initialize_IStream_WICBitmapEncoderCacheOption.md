# CGpWmpEncoder::Initialize(IStream *,WICBitmapEncoderCacheOption)

- ea: `0x18003acb0`
- end: `0x18003adc0`
- name: `?Initialize@CGpWmpEncoder@@UEAAJPEAUIStream@@W4WICBitmapEncoderCacheOption@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(CGpWmpEncoder *__hidden this, struct IStream *, enum WICBitmapEncoderCacheOption)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002de30`
- `0x18003acb0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003acd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003acd3`

## pseudocode

```c
__int64 __fastcall CGpWmpEncoder::Initialize(CGpWmpEncoder *this, struct IStream *a2, __int64 a3)
{
  char *v3; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int v7; // edi
  __int64 v8; // rcx
  int v10; // [rsp+30h] [rbp-10h] BYREF
  char *v11; // [rsp+38h] [rbp-8h] BYREF
  __int16 v12; // [rsp+60h] [rbp+20h] BYREF
  __int16 v13; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+78h] [rbp+38h] BYREF

  v3 = (char *)this - 56;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v11 = v3;
  if ( LOBYTE(v5[1].DebugInfo) )
    EnterCriticalSection(v5);
  if ( a2 )
  {
    if ( *((_DWORD *)this - 16) == 1 )
    {
      *((_QWORD *)this + 2) = a2;
      ((void (__fastcall *)(struct IStream *, struct IStream *, __int64))a2->lpVtbl->AddRef)(a2, a2, a3);
      v8 = *((_QWORD *)this + 2);
      v10 = 0;
      v12 = 18761;
      v14 = 0;
      v13 = 444;
      v7 = (*(__int64 (__fastcall **)(__int64, __int16 *, __int64, int *))(*(_QWORD *)v8 + 32LL))(v8, &v12, 2, &v14);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, __int16 *, __int64, int *))(**((_QWORD **)this + 2) + 32LL))(
               *((_QWORD *)this + 2),
               &v13,
               2,
               &v14);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64, int *))(**((_QWORD **)this + 2) + 32LL))(
                 *((_QWORD *)this + 2),
                 &v10,
                 4,
                 &v14);
          if ( v7 >= 0 )
          {
            *((_DWORD *)this + 12) = 4;
            *((_DWORD *)this - 16) = 2;
          }
        }
      }
    }
    else
    {
      v7 = -2003292412;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003acb0  push    rbp
0x18003acb2  push    rbx
0x18003acb3  push    rdi
0x18003acb4  mov     rbp, rsp
0x18003acb7  sub     rsp, 40h
0x18003acbb  lea     rax, [rcx-38h]
0x18003acbf  mov     rbx, rcx
0x18003acc2  lea     rcx, [rax+8]; lpCriticalSection
0x18003acc6  mov     [rbp+var_8], rax
0x18003acca  cmp     byte ptr [rcx+28h], 0
0x18003acce  mov     rdi, rdx
0x18003acd1  jz      short loc_18003ACDF
0x18003acd3  call    cs:__imp_EnterCriticalSection
0x18003acda  nop     dword ptr [rax+rax+00h]
0x18003acdf  test    rdi, rdi
0x18003ace2  jnz     short loc_18003ACEE
0x18003ace4  mov     edi, 80070057h
0x18003ace9  jmp     loc_18003ADAC
0x18003acee  cmp     dword ptr [rbx-40h], 1
0x18003acf2  jnz     loc_18003ADA7
0x18003acf8  mov     [rbx+10h], rdi
0x18003acfc  mov     rcx, rdi
0x18003acff  mov     rax, [rdi]
0x18003ad02  mov     rax, [rax+8]
0x18003ad06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad0b  mov     rcx, [rbx+10h]
0x18003ad0f  lea     r9, [rbp+arg_18]
0x18003ad13  mov     eax, 4949h
0x18003ad18  mov     [rbp+var_10], 0
0x18003ad1f  mov     [rbp+arg_0], ax
0x18003ad23  lea     rdx, [rbp+arg_0]
0x18003ad27  mov     eax, 1BCh
0x18003ad2c  mov     [rbp+arg_18], 0
0x18003ad33  mov     [rbp+arg_8], ax
0x18003ad37  mov     r8d, 2
0x18003ad3d  mov     rax, [rcx]
0x18003ad40  mov     rax, [rax+20h]
0x18003ad44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad49  mov     edi, eax
0x18003ad4b  test    eax, eax
0x18003ad4d  js      short loc_18003ADAC
0x18003ad4f  mov     rcx, [rbx+10h]
0x18003ad53  lea     r9, [rbp+arg_18]
0x18003ad57  mov     r8d, 2
0x18003ad5d  lea     rdx, [rbp+arg_8]
0x18003ad61  mov     rax, [rcx]
0x18003ad64  mov     rax, [rax+20h]
0x18003ad68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad6d  mov     edi, eax
0x18003ad6f  test    eax, eax
0x18003ad71  js      short loc_18003ADAC
0x18003ad73  mov     rcx, [rbx+10h]
0x18003ad77  lea     r9, [rbp+arg_18]
0x18003ad7b  mov     r8d, 4
0x18003ad81  lea     rdx, [rbp+var_10]
0x18003ad85  mov     rax, [rcx]
0x18003ad88  mov     rax, [rax+20h]
0x18003ad8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad91  mov     edi, eax
0x18003ad93  test    eax, eax
0x18003ad95  js      short loc_18003ADAC
0x18003ad97  mov     dword ptr [rbx+30h], 4
0x18003ad9e  mov     dword ptr [rbx-40h], 2
0x18003ada5  jmp     short loc_18003ADAC
0x18003ada7  mov     edi, 88982F04h
0x18003adac  lea     rcx, [rbp+var_8]
0x18003adb0  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003adb5  mov     eax, edi
0x18003adb7  add     rsp, 40h
0x18003adbb  pop     rdi
0x18003adbc  pop     rbx
0x18003adbd  pop     rbp
0x18003adbe  retn
```
