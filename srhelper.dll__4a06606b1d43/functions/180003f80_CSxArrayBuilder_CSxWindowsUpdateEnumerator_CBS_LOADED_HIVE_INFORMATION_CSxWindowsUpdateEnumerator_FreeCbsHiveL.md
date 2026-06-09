# CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::Append(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)

- ea: `0x180003f80`
- end: `0x180004085`
- name: `?Append@?$CSxArrayBuilder@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@$1?_FreeCbsHiveLoadInformation@2@SAXPEAU12@@Z$1??$SxDefaultInit@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX0@Z$1??$SxDefaultTransfer@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX00@Z@@QEAAJPEAU_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800055a4`

## callees

- `0x180003f80`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004030`
- `ole32!CoTaskMemFree` at `0x180004030`
- `ole32!CoTaskMemRealloc` at `0x18000400e`
- `ole32!CoTaskMemRealloc` at `0x18000400e`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&public: static void CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::Append(
        __int64 a1,
        __int64 a2)
{
  int v4; // edi
  unsigned int v5; // eax
  unsigned int v6; // esi
  unsigned int v7; // ebx
  LPVOID v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax

  if ( a2 )
  {
    v5 = *(_DWORD *)(a1 + 16);
    v6 = v5 + 1;
    if ( v5 + 1 < v5 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v4 = 0;
      if ( v6 > *(_DWORD *)(a1 + 20) )
      {
        v7 = 64;
        if ( v6 > 0x40 )
        {
          v7 = 256;
          if ( v6 > 0x100 )
          {
            v7 = 1024;
            if ( v6 > 0x400 )
            {
              v7 = 4096;
              if ( v6 > 0x1000 )
              {
                v7 = 0x4000;
                if ( v6 > 0x4000 )
                {
                  v7 = (v5 + 0x10000) & 0xFFFF0000;
                  if ( v7 < v6 )
                    v7 = v5 + 1;
                }
              }
            }
          }
        }
        if ( is_mul_ok(v7, 0x18u) )
        {
          v8 = CoTaskMemRealloc(*(LPVOID *)(a1 + 8), 24LL * v7);
          if ( v8 )
          {
            *(_QWORD *)(a1 + 8) = v8;
            *(_DWORD *)(a1 + 20) = v7;
          }
          else
          {
            v4 = -2147024882;
          }
        }
        else
        {
          v4 = -2147024362;
        }
      }
      CoTaskMemFree(0);
      if ( v4 >= 0 )
      {
        v9 = 3LL * *(unsigned int *)(a1 + 16);
        v10 = *(_QWORD *)(a1 + 8);
        *(_OWORD *)(v10 + 8 * v9) = *(_OWORD *)a2;
        *(_QWORD *)(v10 + 8 * v9 + 16) = *(_QWORD *)(a2 + 16);
        *(_OWORD *)a2 = 0;
        *(_QWORD *)(a2 + 16) = 0;
        *(_DWORD *)(a1 + 16) = v6;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003f80  mov     [rsp+arg_0], rbx
0x180003f85  mov     [rsp+arg_10], rbp
0x180003f8a  push    rsi
0x180003f8b  push    rdi
0x180003f8c  push    r14
0x180003f8e  sub     rsp, 20h
0x180003f92  mov     r14, rdx
0x180003f95  mov     rbp, rcx
0x180003f98  test    rdx, rdx
0x180003f9b  jnz     short loc_180003FA7
0x180003f9d  mov     edi, 80070057h
0x180003fa2  jmp     loc_180004070
0x180003fa7  mov     eax, [rcx+10h]
0x180003faa  lea     esi, [rax+1]
0x180003fad  cmp     esi, eax
0x180003faf  jb      loc_18000406B
0x180003fb5  xor     edi, edi
0x180003fb7  cmp     esi, [rcx+14h]
0x180003fba  jbe     short loc_18000402E
0x180003fbc  lea     ebx, [rdi+40h]
0x180003fbf  cmp     esi, ebx
0x180003fc1  jbe     short loc_180003FF8
0x180003fc3  mov     ebx, 100h
0x180003fc8  cmp     esi, ebx
0x180003fca  jbe     short loc_180003FF8
0x180003fcc  mov     ebx, 400h
0x180003fd1  cmp     esi, ebx
0x180003fd3  jbe     short loc_180003FF8
0x180003fd5  mov     ebx, 1000h
0x180003fda  cmp     esi, ebx
0x180003fdc  jbe     short loc_180003FF8
0x180003fde  mov     ebx, 4000h
0x180003fe3  cmp     esi, ebx
0x180003fe5  jbe     short loc_180003FF8
0x180003fe7  lea     ebx, [rsi+0FFFFh]
0x180003fed  and     ebx, 0FFFF0000h
0x180003ff3  cmp     ebx, esi
0x180003ff5  cmovb   ebx, esi
0x180003ff8  mov     ecx, ebx
0x180003ffa  mov     eax, 18h
0x180003fff  mul     rcx
0x180004002  test    rdx, rdx
0x180004005  jnz     short loc_180004029
0x180004007  mov     rcx, [rbp+8]; pv
0x18000400b  mov     rdx, rax; cb
0x18000400e  call    cs:__imp_CoTaskMemRealloc
0x180004014  test    rax, rax
0x180004017  jnz     short loc_180004020
0x180004019  mov     edi, 8007000Eh
0x18000401e  jmp     short loc_18000402E
0x180004020  mov     [rbp+8], rax
0x180004024  mov     [rbp+14h], ebx
0x180004027  jmp     short loc_18000402E
0x180004029  mov     edi, 80070216h
0x18000402e  xor     ecx, ecx; pv
0x180004030  call    cs:__imp_CoTaskMemFree
0x180004036  test    edi, edi
0x180004038  js      short loc_180004070
0x18000403a  mov     eax, [rbp+10h]
0x18000403d  movups  xmm0, xmmword ptr [r14]
0x180004041  lea     rcx, [rax+rax*2]
0x180004045  mov     rax, [rbp+8]
0x180004049  movups  xmmword ptr [rax+rcx*8], xmm0
0x18000404d  movsd   xmm1, qword ptr [r14+10h]
0x180004053  xorps   xmm0, xmm0
0x180004056  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18000405c  xor     eax, eax
0x18000405e  movups  xmmword ptr [r14], xmm0
0x180004062  mov     [r14+10h], rax
0x180004066  mov     [rbp+10h], esi
0x180004069  jmp     short loc_180004070
0x18000406b  mov     edi, 80070216h
0x180004070  mov     rbx, [rsp+38h+arg_0]
0x180004075  mov     eax, edi
0x180004077  mov     rbp, [rsp+38h+arg_10]
0x18000407c  add     rsp, 20h
0x180004080  pop     r14
0x180004082  pop     rdi
0x180004083  pop     rsi
0x180004084  retn
```
