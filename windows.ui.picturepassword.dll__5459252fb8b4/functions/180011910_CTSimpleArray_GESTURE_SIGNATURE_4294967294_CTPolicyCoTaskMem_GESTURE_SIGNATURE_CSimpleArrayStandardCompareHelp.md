# CTSimpleArray<GESTURE_SIGNATURE,4294967294,CTPolicyCoTaskMem<GESTURE_SIGNATURE>,CSimpleArrayStandardCompareHelper<GESTURE_SIGNATURE>,CSimpleArrayStandardMergeHelper<GESTURE_SIGNATURE>>::_EnsureCapacity(unsigned __int64,unsigned __int64)

- ea: `0x180011910`
- end: `0x1800119e4`
- name: `?_EnsureCapacity@?$CTSimpleArray@UGESTURE_SIGNATURE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UGESTURE_SIGNATURE@@@@V?$CSimpleArrayStandardCompareHelper@UGESTURE_SIGNATURE@@@@V?$CSimpleArrayStandardMergeHelper@UGESTURE_SIGNATURE@@@@@@QEAAJ_K0@Z`
- size: `212`
- prototype: `int __fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e9f8`
- `0x1800140fc`
- `0x1800149e4`

## callees

- `0x18000a64c`
- `0x180010a80`
- `0x180011910`

## pseudocode

```c
int __fastcall CTSimpleArray<GESTURE_SIGNATURE,4294967294,CTPolicyCoTaskMem<GESTURE_SIGNATURE>,CSimpleArrayStandardCompareHelper<GESTURE_SIGNATURE>,CSimpleArrayStandardMergeHelper<GESTURE_SIGNATURE>>::_EnsureCapacity(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  int result; // eax
  unsigned __int64 v6; // r10
  unsigned __int64 v7; // r9
  __int64 v8; // r10
  unsigned __int64 v9; // rcx
  unsigned int v10; // edx
  void *v11; // rcx
  void *v12; // r10
  void *v13; // r9
  void *v14; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = a3;
  v3 = 4294967294LL;
  result = -2147024774;
  if ( a2 <= 0xFFFFFFFE )
  {
    v6 = a1[3];
    result = 0;
    if ( a2 > v6 )
    {
      v15 = 0;
      result = ULongLongMult(v6, 2u, &v15);
      if ( result >= 0 )
      {
        v9 = v15;
        if ( v15 - v8 > 0x1000 )
          v9 = v8 + 4096;
        if ( v7 > v9 || v9 <= 0xFFFFFFFE )
        {
          v3 = v9;
          if ( v7 > v9 )
            v3 = v7;
        }
        v14 = 0;
        v15 = 0;
        result = ULongLongMult(v3, 0x14u, &v15);
        if ( result >= 0 )
        {
          result = CTCoAllocPolicy::Realloc(v11, v10, v12, v15, &v14);
          v13 = v14;
          if ( result >= 0 )
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
0x180011910  mov     r11, rsp
0x180011913  mov     [r11+8], rbx
0x180011917  mov     [r11+18h], r8
0x18001191b  push    rdi
0x18001191c  sub     rsp, 30h
0x180011920  mov     ebx, 0FFFFFFFEh
0x180011925  mov     r9, rdx
0x180011928  mov     rdi, rcx
0x18001192b  mov     eax, 8007007Ah
0x180011930  cmp     rdx, rbx
0x180011933  ja      loc_1800119D9
0x180011939  mov     r10, [rcx+18h]
0x18001193d  xor     eax, eax
0x18001193f  cmp     rdx, r10
0x180011942  jbe     loc_1800119D9
0x180011948  lea     r8, [r11+18h]; unsigned __int64 *
0x18001194c  mov     [r11+18h], rax
0x180011950  lea     edx, [rax+2]; unsigned __int64
0x180011953  mov     rcx, r10; unsigned __int64
0x180011956  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001195b  test    eax, eax
0x18001195d  js      short loc_1800119D9
0x18001195f  mov     rcx, [rsp+38h+arg_10]
0x180011964  mov     rax, rcx
0x180011967  sub     rax, r10
0x18001196a  cmp     rax, 1000h
0x180011970  jbe     short loc_180011979
0x180011972  lea     rcx, [r10+1000h]
0x180011979  cmp     r9, rcx
0x18001197c  ja      short loc_180011983
0x18001197e  cmp     rcx, rbx
0x180011981  ja      short loc_18001198D
0x180011983  cmp     r9, rcx
0x180011986  mov     rbx, rcx
0x180011989  cmova   rbx, r9
0x18001198d  mov     r10, [rdi]
0x180011990  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x180011995  xor     r9d, r9d
0x180011998  mov     rcx, rbx; unsigned __int64
0x18001199b  mov     [rsp+38h+arg_8], r9
0x1800119a0  mov     [rsp+38h+arg_10], r9
0x1800119a5  lea     edx, [r9+14h]; unsigned __int64
0x1800119a9  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800119ae  test    eax, eax
0x1800119b0  js      short loc_1800119D9
0x1800119b2  mov     r9, [rsp+38h+arg_10]; unsigned __int64
0x1800119b7  lea     rax, [rsp+38h+arg_8]
0x1800119bc  mov     r8, r10; void *
0x1800119bf  mov     [rsp+38h+var_18], rax; void **
0x1800119c4  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1800119c9  mov     r9, [rsp+38h+arg_8]
0x1800119ce  test    eax, eax
0x1800119d0  js      short loc_1800119D9
0x1800119d2  mov     [rdi+18h], rbx
0x1800119d6  mov     [rdi], r9
0x1800119d9  mov     rbx, [rsp+38h+arg_0]
0x1800119de  add     rsp, 30h
0x1800119e2  pop     rdi
0x1800119e3  retn
```
