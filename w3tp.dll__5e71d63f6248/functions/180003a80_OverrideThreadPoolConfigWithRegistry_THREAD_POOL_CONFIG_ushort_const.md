# OverrideThreadPoolConfigWithRegistry(THREAD_POOL_CONFIG *,ushort const *)

- ea: `0x180003a80`
- end: `0x180003bd1`
- name: `?OverrideThreadPoolConfigWithRegistry@@YAJPEAUTHREAD_POOL_CONFIG@@PEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct THREAD_POOL_CONFIG *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003d80`

## callees

- `0x180003878`
- `0x180003a80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ab1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ab1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003bbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003bbe`

## string_xrefs

- `0x180003ad7`: `MaxPoolThreads`
- `0x180003aee`: `ThreadTimeout`
- `0x180003b05`: `PoolThreadLimit`
- `0x180003b1b`: `ThreadPoolStartupThreadCount`
- `0x180003b32`: `ThreadPoolMaxCPU`
- `0x180003b48`: `ThreadPoolMaxContextSwitch`
- `0x180003b5f`: `ThreadPoolStartDelay`
- `0x180003b76`: `ThreadPoolExactThreadCount`
- `0x180003b8d`: `ThreadPoolReserveStackSize`
- `0x180003ba4`: `ThreadPoolUseIdealCpu`

## pseudocode

```c
__int64 __fastcall OverrideThreadPoolConfigWithRegistry(struct THREAD_POOL_CONFIG *a1, const unsigned __int16 *a2)
{
  unsigned int RegDword; // eax
  unsigned int v4; // r8d
  HKEY v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // r8d
  HKEY v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  HKEY v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // r8d
  HKEY v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // r8d
  HKEY v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // r8d
  HKEY v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // r8d
  HKEY v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // r8d
  HKEY v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // r8d
  HKEY v29; // rcx
  unsigned int v30; // eax
  unsigned int v31; // r8d
  HKEY v32; // rcx
  unsigned int v33; // eax
  HKEY v34; // rcx
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey) )
  {
    RegDword = I_ThreadPoolReadRegDword(hKey, L"MaxConcurrency", *((_DWORD *)a1 + 6));
    v4 = *((_DWORD *)a1 + 2);
    v5 = hKey;
    *((_DWORD *)a1 + 6) = RegDword;
    v6 = I_ThreadPoolReadRegDword(v5, L"MaxPoolThreads", v4);
    v7 = *((_DWORD *)a1 + 3);
    v8 = hKey;
    *((_DWORD *)a1 + 2) = v6;
    v9 = I_ThreadPoolReadRegDword(v8, L"ThreadTimeout", v7);
    v10 = *((_DWORD *)a1 + 1);
    v11 = hKey;
    *((_DWORD *)a1 + 3) = v9;
    v12 = I_ThreadPoolReadRegDword(v11, L"PoolThreadLimit", v10);
    v13 = *(_DWORD *)a1;
    v14 = hKey;
    *((_DWORD *)a1 + 1) = v12;
    v15 = I_ThreadPoolReadRegDword(v14, L"ThreadPoolStartupThreadCount", v13);
    v16 = *((_DWORD *)a1 + 5);
    v17 = hKey;
    *(_DWORD *)a1 = v15;
    v18 = I_ThreadPoolReadRegDword(v17, L"ThreadPoolMaxCPU", v16);
    v19 = *((_DWORD *)a1 + 7);
    v20 = hKey;
    *((_DWORD *)a1 + 5) = v18;
    v21 = I_ThreadPoolReadRegDword(v20, L"ThreadPoolMaxContextSwitch", v19);
    v22 = *((_DWORD *)a1 + 8);
    v23 = hKey;
    *((_DWORD *)a1 + 7) = v21;
    v24 = I_ThreadPoolReadRegDword(v23, L"ThreadPoolStartDelay", v22);
    v25 = *((_DWORD *)a1 + 9);
    v26 = hKey;
    *((_DWORD *)a1 + 8) = v24;
    v27 = I_ThreadPoolReadRegDword(v26, L"ThreadPoolExactThreadCount", v25);
    v28 = *((_DWORD *)a1 + 4);
    v29 = hKey;
    *((_DWORD *)a1 + 9) = v27;
    v30 = I_ThreadPoolReadRegDword(v29, L"ThreadPoolReserveStackSize", v28);
    v31 = *((_DWORD *)a1 + 11);
    v32 = hKey;
    *((_DWORD *)a1 + 4) = v30;
    v33 = I_ThreadPoolReadRegDword(v32, L"ThreadPoolUseIdealCpu", v31);
    v34 = hKey;
    *((_DWORD *)a1 + 11) = v33;
    RegCloseKey(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x180003a80  mov     [rsp-8+arg_0], rbx
0x180003a85  push    rbp
0x180003a86  mov     rbp, rsp
0x180003a89  sub     rsp, 30h
0x180003a8d  mov     rbx, rcx
0x180003a90  mov     [rbp+hKey], 0
0x180003a98  lea     rax, [rbp+hKey]
0x180003a9c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003aa3  mov     r9d, 20019h; samDesired
0x180003aa9  mov     [rsp+30h+phkResult], rax; phkResult
0x180003aae  xor     r8d, r8d; ulOptions
0x180003ab1  call    cs:__imp_RegOpenKeyExW
0x180003ab7  test    eax, eax
0x180003ab9  jnz     loc_180003BC4
0x180003abf  mov     r8d, [rbx+18h]; unsigned int
0x180003ac3  lea     rdx, aMaxconcurrency; "MaxConcurrency"
0x180003aca  mov     rcx, [rbp+hKey]; HKEY
0x180003ace  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003ad3  mov     r8d, [rbx+8]; unsigned int
0x180003ad7  lea     rdx, aMaxpoolthreads; "MaxPoolThreads"
0x180003ade  mov     rcx, [rbp+hKey]; HKEY
0x180003ae2  mov     [rbx+18h], eax
0x180003ae5  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003aea  mov     r8d, [rbx+0Ch]; unsigned int
0x180003aee  lea     rdx, aThreadtimeout; "ThreadTimeout"
0x180003af5  mov     rcx, [rbp+hKey]; HKEY
0x180003af9  mov     [rbx+8], eax
0x180003afc  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003b01  mov     r8d, [rbx+4]; unsigned int
0x180003b05  lea     rdx, aPoolthreadlimi; "PoolThreadLimit"
0x180003b0c  mov     rcx, [rbp+hKey]; HKEY
0x180003b10  mov     [rbx+0Ch], eax
0x180003b13  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003b18  mov     r8d, [rbx]; unsigned int
0x180003b1b  lea     rdx, aThreadpoolstar; "ThreadPoolStartupThreadCount"
0x180003b22  mov     rcx, [rbp+hKey]; HKEY
0x180003b26  mov     [rbx+4], eax
0x180003b29  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003b2e  mov     r8d, [rbx+14h]; unsigned int
0x180003b32  lea     rdx, aThreadpoolmaxc; "ThreadPoolMaxCPU"
0x180003b39  mov     rcx, [rbp+hKey]; HKEY
0x180003b3d  mov     [rbx], eax
0x180003b3f  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003b44  mov     r8d, [rbx+1Ch]; unsigned int
0x180003b48  lea     rdx, aThreadpoolmaxc_0; "ThreadPoolMaxContextSwitch"
0x180003b4f  mov     rcx, [rbp+hKey]; HKEY
0x180003b53  mov     [rbx+14h], eax
0x180003b56  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003b5b  mov     r8d, [rbx+20h]; unsigned int
0x180003b5f  lea     rdx, aThreadpoolstar_0; "ThreadPoolStartDelay"
0x180003b66  mov     rcx, [rbp+hKey]; HKEY
0x180003b6a  mov     [rbx+1Ch], eax
0x180003b6d  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003b72  mov     r8d, [rbx+24h]; unsigned int
0x180003b76  lea     rdx, aThreadpoolexac; "ThreadPoolExactThreadCount"
0x180003b7d  mov     rcx, [rbp+hKey]; HKEY
0x180003b81  mov     [rbx+20h], eax
0x180003b84  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003b89  mov     r8d, [rbx+10h]; unsigned int
0x180003b8d  lea     rdx, aThreadpoolrese; "ThreadPoolReserveStackSize"
0x180003b94  mov     rcx, [rbp+hKey]; HKEY
0x180003b98  mov     [rbx+24h], eax
0x180003b9b  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003ba0  mov     r8d, [rbx+2Ch]; unsigned int
0x180003ba4  lea     rdx, aThreadpoolusei; "ThreadPoolUseIdealCpu"
0x180003bab  mov     rcx, [rbp+hKey]; HKEY
0x180003baf  mov     [rbx+10h], eax
0x180003bb2  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003bb7  mov     rcx, [rbp+hKey]; hKey
0x180003bbb  mov     [rbx+2Ch], eax
0x180003bbe  call    cs:__imp_RegCloseKey
0x180003bc4  mov     rbx, [rsp+30h+arg_0]
0x180003bc9  xor     eax, eax
0x180003bcb  add     rsp, 30h
0x180003bcf  pop     rbp
0x180003bd0  retn
```
