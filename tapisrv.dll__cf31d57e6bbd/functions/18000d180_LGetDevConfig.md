# LGetDevConfig

- ea: `0x18000d180`
- end: `0x18000d351`
- name: `LGetDevConfig`
- size: `465`
- prototype: `__int64 __fastcall(int, _DWORD *, unsigned int, unsigned int *, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180028100`

## callees

- `0x1800070e8`
- `0x1800072e4`
- `0x18000d180`
- `0x180017b74`
- `0x180019fcc`
- `0x18001c854`
- `0x18002c8d4`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000d280`
- `KERNEL32!HeapAlloc` at `0x18000d280`
- `KERNEL32!lstrlenW` at `0x18000d263`
- `KERNEL32!lstrlenW` at `0x18000d263`

## pseudocode

```c
__int64 __fastcall LGetDevConfig(int a1, _DWORD *a2, unsigned int a3, unsigned int *a4, _DWORD *a5)
{
  __int64 result; // rax
  int v9; // eax
  int v10; // eax
  size_t v11; // r14
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  int v14; // eax
  __int64 v15; // [rsp+70h] [rbp+1Fh] BYREF
  __int64 v16; // [rsp+78h] [rbp+27h] BYREF
  __int64 v17; // [rsp+80h] [rbp+2Fh] BYREF
  HANDLE TargetHandle; // [rsp+88h] [rbp+37h] BYREF
  __int64 v19; // [rsp+B8h] [rbp+67h] BYREF
  int v20; // [rsp+C0h] [rbp+6Fh] BYREF

  result = a3;
  LODWORD(v15) = 0;
  v20 = 0;
  TargetHandle = 0;
  v17 = 0;
  LODWORD(v19) = 0;
  v16 = 0;
  if ( a2[3] > a3 || (result = IsBadStringParam(a3, (__int64)a4, a2[4]), (_DWORD)result) )
  {
    *a2 = -2147483576;
  }
  else
  {
    v9 = LineProlog(
           a1,
           3,
           0,
           (int)&v20,
           a2[2],
           &TargetHandle,
           (__int64)&v15,
           29,
           (__int64)&v17,
           0,
           0,
           (__int64)&v19,
           (__int64)&v16);
    *a2 = v9;
    if ( !v9 )
    {
      v10 = lstrlenW((LPCWSTR)((char *)a4 + (unsigned int)a2[4])) + 1;
      v11 = 2LL * v10;
      v12 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * v10));
      v13 = v12;
      if ( v12 )
      {
        StringCbCopyW(v12, v11, (STRSAFE_LPCWSTR)((char *)a4 + (unsigned int)a2[4]));
        if ( (unsigned int)InitTapiStruct(a4, a2[3], 0x18u, 1) )
        {
          if ( *(_DWORD *)(v16 + 32) )
          {
            ServerFree(v13);
            *a2 = -2147483582;
          }
          else
          {
            v14 = ((__int64 (__fastcall *)(_QWORD, unsigned int *, wchar_t *))v17)((unsigned int)v20, a4, v13);
            *a2 = v14;
            if ( !v14 )
            {
              a2[3] = 0;
              *a5 = a4[2] + 60;
            }
            ServerFree(v13);
          }
        }
        else
        {
          ServerFree(v13);
          *a2 = -2147483571;
        }
      }
      else
      {
        *a2 = -2147483580;
      }
    }
    return LineEpilogSync(a2, TargetHandle, (unsigned int)v15, (unsigned int)v19);
  }
  return result;
}

```

## disassembly

```asm
0x18000d180  mov     [rsp-8+arg_0], rbx
0x18000d185  mov     [rsp-8+arg_18], rsi
0x18000d18a  push    rbp
0x18000d18b  push    rdi
0x18000d18c  push    r14
0x18000d18e  lea     rbp, [rsp-3Fh]
0x18000d193  sub     rsp, 90h
0x18000d19a  mov     rsi, r9
0x18000d19d  mov     eax, r8d
0x18000d1a0  mov     rbx, rdx
0x18000d1a3  mov     rdi, rcx
0x18000d1a6  mov     dword ptr [rbp+4Fh+var_30], 0
0x18000d1ad  mov     [rbp+4Fh+arg_10], 0
0x18000d1b4  mov     [rbp+4Fh+TargetHandle], 0
0x18000d1bc  mov     [rbp+4Fh+var_20], 0
0x18000d1c4  mov     dword ptr [rbp+4Fh+arg_8], 0
0x18000d1cb  mov     [rbp+4Fh+var_28], 0
0x18000d1d3  cmp     [rdx+0Ch], r8d
0x18000d1d7  ja      loc_18000D333
0x18000d1dd  mov     r8d, [rdx+10h]
0x18000d1e1  mov     ecx, eax
0x18000d1e3  mov     rdx, r9
0x18000d1e6  call    IsBadStringParam
0x18000d1eb  test    eax, eax
0x18000d1ed  jnz     loc_18000D333
0x18000d1f3  lea     rax, [rbp+4Fh+var_28]
0x18000d1f7  xor     r8d, r8d; int
0x18000d1fa  mov     [rsp+0A0h+var_40], rax; __int64
0x18000d1ff  lea     r9, [rbp+4Fh+arg_10]; int
0x18000d203  lea     rax, [rbp+4Fh+arg_8]
0x18000d207  mov     rcx, rdi; int
0x18000d20a  mov     [rsp+0A0h+var_48], rax; __int64
0x18000d20f  lea     rax, [rbp+4Fh+var_20]
0x18000d213  mov     [rsp+0A0h+var_50], 0; int
0x18000d21b  lea     edx, [r8+3]; int
0x18000d21f  mov     [rsp+0A0h+var_58], 0; __int64
0x18000d228  mov     [rsp+0A0h+var_60], rax; __int64
0x18000d22d  lea     rax, [rbp+4Fh+var_30]
0x18000d231  mov     [rsp+0A0h+var_68], 1Dh; int
0x18000d239  mov     [rsp+0A0h+var_70], rax; __int64
0x18000d23e  lea     rax, [rbp+4Fh+TargetHandle]
0x18000d242  mov     [rsp+0A0h+lpTargetHandle], rax; lpTargetHandle
0x18000d247  mov     eax, [rbx+8]
0x18000d24a  mov     [rsp+0A0h+var_80], eax; int
0x18000d24e  call    LineProlog
0x18000d253  mov     [rbx], eax
0x18000d255  test    eax, eax
0x18000d257  jnz     loc_18000D31D
0x18000d25d  mov     ecx, [rbx+10h]
0x18000d260  add     rcx, rsi; lpString
0x18000d263  call    cs:__imp_lstrlenW
0x18000d269  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18000d270  mov     edx, 8; dwFlags
0x18000d275  inc     eax
0x18000d277  movsxd  r14, eax
0x18000d27a  add     r14, r14
0x18000d27d  mov     r8d, r14d; dwBytes
0x18000d280  call    cs:__imp_HeapAlloc
0x18000d286  mov     rdi, rax
0x18000d289  test    rax, rax
0x18000d28c  jnz     short loc_18000D299
0x18000d28e  mov     dword ptr [rbx], 80000044h
0x18000d294  jmp     loc_18000D31D
0x18000d299  mov     r8d, [rbx+10h]
0x18000d29d  mov     rdx, r14; cbDest
0x18000d2a0  add     r8, rsi; pszSrc
0x18000d2a3  mov     rcx, rdi; pszDest
0x18000d2a6  call    StringCbCopyW
0x18000d2ab  mov     edx, [rbx+0Ch]
0x18000d2ae  mov     r9d, 1
0x18000d2b4  mov     rcx, rsi
0x18000d2b7  lea     r8d, [r9+17h]
0x18000d2bb  call    InitTapiStruct
0x18000d2c0  test    eax, eax
0x18000d2c2  jnz     short loc_18000D2D4
0x18000d2c4  mov     rcx, rdi; lpMem
0x18000d2c7  call    ServerFree
0x18000d2cc  mov     dword ptr [rbx], 8000004Dh
0x18000d2d2  jmp     short loc_18000D31D
0x18000d2d4  mov     rax, [rbp+4Fh+var_28]
0x18000d2d8  cmp     dword ptr [rax+20h], 0
0x18000d2dc  jz      short loc_18000D2EE
0x18000d2de  mov     rcx, rdi; lpMem
0x18000d2e1  call    ServerFree
0x18000d2e6  mov     dword ptr [rbx], 80000042h
0x18000d2ec  jmp     short loc_18000D31D
0x18000d2ee  mov     ecx, [rbp+4Fh+arg_10]
0x18000d2f1  mov     r8, rdi
0x18000d2f4  mov     rax, [rbp+4Fh+var_20]
0x18000d2f8  mov     rdx, rsi
0x18000d2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d300  mov     [rbx], eax
0x18000d302  test    eax, eax
0x18000d304  jnz     short loc_18000D315
0x18000d306  mov     [rbx+0Ch], eax
0x18000d309  mov     ecx, [rsi+8]
0x18000d30c  mov     rax, [rbp+4Fh+arg_20]
0x18000d310  add     ecx, 3Ch ; '<'
0x18000d313  mov     [rax], ecx
0x18000d315  mov     rcx, rdi; lpMem
0x18000d318  call    ServerFree
0x18000d31d  mov     r9d, dword ptr [rbp+4Fh+arg_8]
0x18000d321  mov     rcx, rbx
0x18000d324  mov     r8d, dword ptr [rbp+4Fh+var_30]
0x18000d328  mov     rdx, [rbp+4Fh+TargetHandle]
0x18000d32c  call    LineEpilogSync
0x18000d331  jmp     short loc_18000D339
0x18000d333  mov     dword ptr [rbx], 80000048h
0x18000d339  lea     r11, [rsp+0A0h+var_10]
0x18000d341  mov     rbx, [r11+20h]
0x18000d345  mov     rsi, [r11+38h]
0x18000d349  mov     rsp, r11
0x18000d34c  pop     r14
0x18000d34e  pop     rdi
0x18000d34f  pop     rbp
0x18000d350  retn
```
