# CTSimpleArray<DriveCacheEntry,4294967294,CTPolicyCoTaskMem<DriveCacheEntry>,CSimpleArrayStandardCompareHelper<DriveCacheEntry>,CSimpleArrayStandardMergeHelper<DriveCacheEntry>>::_EnsureCapacity(unsigned __int64,unsigned __int64)

- ea: `0x18003f608`
- end: `0x18003f6fc`
- name: `?_EnsureCapacity@?$CTSimpleArray@UDriveCacheEntry@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UDriveCacheEntry@@@@V?$CSimpleArrayStandardCompareHelper@UDriveCacheEntry@@@@V?$CSimpleArrayStandardMergeHelper@UDriveCacheEntry@@@@@@QEAAJ_K0@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ed6c`

## callees

- `0x1800282f8`
- `0x1800364ac`
- `0x18003f588`
- `0x18003f608`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003f6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003f6b2`

## pseudocode

```c
__int64 __fastcall CTSimpleArray<DriveCacheEntry,4294967294,CTPolicyCoTaskMem<DriveCacheEntry>,CSimpleArrayStandardCompareHelper<DriveCacheEntry>,CSimpleArrayStandardMergeHelper<DriveCacheEntry>>::_EnsureCapacity(
        _QWORD *a1,
        unsigned __int64 a2,
        SIZE_T a3)
{
  unsigned __int64 v3; // rbx
  __int64 result; // rax
  unsigned __int64 v6; // r10
  SIZE_T v7; // r9
  __int64 v8; // r10
  SIZE_T v9; // rcx
  void *v10; // r9
  SIZE_T v11; // r14
  char *v12; // rax
  char *v13; // rdi
  unsigned __int64 v14; // rax
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF

  cb = a3;
  v3 = 4294967294LL;
  result = 2147942522LL;
  if ( a2 <= 0xFFFFFFFE )
  {
    v6 = a1[3];
    result = 0;
    if ( a2 > v6 )
    {
      cb = 0;
      result = ULongLongMult(v6, 2u, &cb);
      if ( (int)result >= 0 )
      {
        v9 = cb;
        if ( cb - v8 > 0x1000 )
          v9 = v8 + 4096;
        if ( v7 > v9 || v9 <= 0xFFFFFFFE )
        {
          v3 = v9;
          if ( v7 > v9 )
            v3 = v7;
        }
        cb = 0;
        result = ULongLongMult(v3, 0x10u, &cb);
        if ( (int)result >= 0 )
        {
          v11 = cb;
          v12 = (char *)CoTaskMemRealloc(v10, cb);
          v13 = v12;
          if ( v12 )
          {
            v14 = CTCoAllocPolicy::_CoTaskMemSize(v12);
            if ( v14 > v11 )
              memset_0(&v13[v11], 0, v14 - v11);
            result = 0;
          }
          else
          {
            result = 2147942414LL;
          }
          if ( (int)result >= 0 )
          {
            a1[3] = v3;
            *a1 = v13;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003f608  mov     [rsp+cb], r8
0x18003f60d  push    rbx
0x18003f60e  push    rsi
0x18003f60f  push    rdi
0x18003f610  push    r14
0x18003f612  sub     rsp, 28h
0x18003f616  mov     ebx, 0FFFFFFFEh
0x18003f61b  mov     r9, rdx
0x18003f61e  mov     rsi, rcx
0x18003f621  mov     eax, 8007007Ah
0x18003f626  cmp     rdx, rbx
0x18003f629  ja      loc_18003F6F2
0x18003f62f  mov     r10, [rcx+18h]
0x18003f633  xor     eax, eax
0x18003f635  cmp     rdx, r10
0x18003f638  jbe     loc_18003F6F2
0x18003f63e  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18003f643  mov     [rsp+48h+cb], rax
0x18003f648  lea     edx, [rax+2]; unsigned __int64
0x18003f64b  mov     rcx, r10; unsigned __int64
0x18003f64e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003f653  test    eax, eax
0x18003f655  js      loc_18003F6F2
0x18003f65b  mov     rcx, [rsp+48h+cb]
0x18003f660  mov     rax, rcx
0x18003f663  sub     rax, r10
0x18003f666  cmp     rax, 1000h
0x18003f66c  jbe     short loc_18003F675
0x18003f66e  lea     rcx, [r10+1000h]
0x18003f675  cmp     r9, rcx
0x18003f678  ja      short loc_18003F67F
0x18003f67a  cmp     rcx, rbx
0x18003f67d  ja      short loc_18003F689
0x18003f67f  cmp     r9, rcx
0x18003f682  mov     rbx, rcx
0x18003f685  cmova   rbx, r9
0x18003f689  mov     r9, [rsi]
0x18003f68c  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18003f691  xor     edi, edi
0x18003f693  mov     rcx, rbx; unsigned __int64
0x18003f696  mov     [rsp+48h+cb], rdi
0x18003f69b  lea     edx, [rdi+10h]; unsigned __int64
0x18003f69e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003f6a3  test    eax, eax
0x18003f6a5  js      short loc_18003F6F2
0x18003f6a7  mov     r14, [rsp+48h+cb]
0x18003f6ac  mov     rcx, r9; pv
0x18003f6af  mov     rdx, r14; cb
0x18003f6b2  call    cs:__imp_CoTaskMemRealloc
0x18003f6b8  mov     rdi, rax
0x18003f6bb  test    rax, rax
0x18003f6be  jz      short loc_18003F6E2
0x18003f6c0  mov     rcx, rax; void *
0x18003f6c3  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18003f6c8  cmp     rax, r14
0x18003f6cb  jbe     short loc_18003F6DE
0x18003f6cd  sub     rax, r14
0x18003f6d0  lea     rcx, [r14+rdi]; void *
0x18003f6d4  mov     r8, rax; Size
0x18003f6d7  xor     edx, edx; Val
0x18003f6d9  call    memset_0
0x18003f6de  xor     eax, eax
0x18003f6e0  jmp     short loc_18003F6E7
0x18003f6e2  mov     eax, 8007000Eh
0x18003f6e7  test    eax, eax
0x18003f6e9  js      short loc_18003F6F2
0x18003f6eb  mov     [rsi+18h], rbx
0x18003f6ef  mov     [rsi], rdi
0x18003f6f2  add     rsp, 28h
0x18003f6f6  pop     r14
0x18003f6f8  pop     rdi
0x18003f6f9  pop     rsi
0x18003f6fa  pop     rbx
0x18003f6fb  retn
```
