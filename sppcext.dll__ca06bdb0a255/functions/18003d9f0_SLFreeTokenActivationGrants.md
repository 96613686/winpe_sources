# SLFreeTokenActivationGrants

- ea: `0x18003d9f0`
- end: `0x18003dad2`
- name: `SLFreeTokenActivationGrants`
- size: `226`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003b1fc`

## callees

- `0x180006c10`
- `0x18003d9f0`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043bd8`
- `0x180043eac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003da75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003da8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003da75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003da8d`

## pseudocode

```c
__int64 __fastcall SLFreeTokenActivationGrants(HLOCAL *hMem, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // rsi
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8

  sub_1800427F4((unsigned int *)byte_180084068, (unsigned int *)qword_18008CB80, a3);
  if ( hMem )
  {
    sub_180042DB0((unsigned int *)&dword_180082B24, (unsigned int *)&dword_18008D58C, v4);
    sub_180042514((unsigned int *)qword_1800835C0, (unsigned int *)byte_18008DD48, v5);
    v6 = 0;
    sub_180042ACC((unsigned int *)qword_1800832D8, (unsigned int *)qword_18008DB30, v7);
    if ( *(_DWORD *)hMem )
    {
      sub_180043BD8((unsigned int *)&dword_18008406C, (unsigned int *)byte_18008CBC8, v8);
      do
      {
        LocalFree(hMem[v6 + 1]);
        hMem[v6 + 1] = 0;
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < *(_DWORD *)hMem );
    }
    LocalFree(hMem);
    sub_180043088((unsigned int *)&dword_180084CBC, (unsigned int *)&dword_18008D894, v9);
  }
  sub_180006C10(0);
  sub_180043EAC((unsigned int *)byte_180085058, (unsigned int *)&dword_18008DD4C, v10);
  return 0;
}

```

## disassembly

```asm
0x18003d9f0  mov     [rsp+arg_0], rbx
0x18003d9f5  mov     [rsp+arg_8], rsi
0x18003d9fa  push    rdi
0x18003d9fb  sub     rsp, 20h
0x18003d9ff  mov     rdi, rcx
0x18003da02  lea     rdx, qword_18008CB80
0x18003da09  lea     rcx, byte_180084068
0x18003da10  call    sub_1800427F4
0x18003da15  test    rdi, rdi
0x18003da18  jz      loc_18003DAA6
0x18003da1e  lea     rdx, dword_18008D58C
0x18003da25  lea     rcx, dword_180082B24
0x18003da2c  call    sub_180042DB0
0x18003da31  lea     rdx, byte_18008DD48
0x18003da38  lea     rcx, qword_1800835C0
0x18003da3f  call    sub_180042514
0x18003da44  lea     rdx, qword_18008DB30
0x18003da4b  xor     esi, esi
0x18003da4d  lea     rcx, qword_1800832D8
0x18003da54  call    sub_180042ACC
0x18003da59  cmp     [rdi], esi
0x18003da5b  jbe     short loc_18003DA8A
0x18003da5d  lea     rdx, byte_18008CBC8
0x18003da64  lea     rcx, dword_18008406C
0x18003da6b  call    sub_180043BD8
0x18003da70  mov     rcx, [rdi+rsi*8+8]; hMem
0x18003da75  call    cs:LocalFree
0x18003da7b  mov     qword ptr [rdi+rsi*8+8], 0
0x18003da84  inc     esi
0x18003da86  cmp     esi, [rdi]
0x18003da88  jb      short loc_18003DA70
0x18003da8a  mov     rcx, rdi; hMem
0x18003da8d  call    cs:LocalFree
0x18003da93  lea     rdx, dword_18008D894
0x18003da9a  lea     rcx, dword_180084CBC
0x18003daa1  call    sub_180043088
0x18003daa6  xor     ecx, ecx
0x18003daa8  call    sub_180006C10
0x18003daad  lea     rdx, dword_18008DD4C
0x18003dab4  lea     rcx, byte_180085058
0x18003dabb  call    sub_180043EAC
0x18003dac0  mov     rbx, [rsp+28h+arg_0]
0x18003dac5  xor     eax, eax
0x18003dac7  mov     rsi, [rsp+28h+arg_8]
0x18003dacc  add     rsp, 20h
0x18003dad0  pop     rdi
0x18003dad1  retn
```
