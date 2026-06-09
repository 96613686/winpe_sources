# ProcessAddedSearchRoots(CAutoDSA<SEARCH_ROOT> *,CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>> const &)

- ea: `0x180022b78`
- end: `0x180022cb9`
- name: `?ProcessAddedSearchRoots@@YAXPEAV?$CAutoDSA@USEARCH_ROOT@@@@AEBV?$CCoSimpleArray@H$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@H@@@@@Z`
- size: `321`
- prototype: `LSTATUS __fastcall(HDSA *, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022840`
- `0x180022aa0`

## callees

- `0x18002195c`
- `0x180022b78`
- `0x180022e44`
- `0x1800234f0`
- `0x18002ff1c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022c9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022c9b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022bcb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022bcb`

## pseudocode

```c
LSTATUS __fastcall ProcessAddedSearchRoots(HDSA *a1, _QWORD *a2)
{
  LSTATUS result; // eax
  int v5; // esi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rdi
  unsigned int v8; // ebx
  int i; // ebp
  PVOID ItemPtr; // r13
  const unsigned __int16 *v11; // r8
  struct CAddRemoveSynchronizer *v12; // [rsp+A0h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+20h] BYREF

  hKey = 0;
  result = RegCreateKeyExW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows Search\\ProcessedSearchRoots",
             0,
             0,
             0,
             0x20006u,
             0,
             &hKey,
             0);
  if ( !result )
  {
    if ( *a1 )
      v5 = *(_DWORD *)*a1;
    else
      v5 = 0;
    v6 = a2[1];
    v7 = 0;
    v8 = 0;
    for ( i = 0; i < v5; ++v8 )
    {
      for ( ; v7 < v6; ++v7 )
      {
        if ( v8 != *(_DWORD *)(*a2 + 4 * v7) )
          break;
        ++v8;
      }
      ItemPtr = DSA_GetItemPtr(*a1, i);
      if ( !(unsigned int)ValidateSearchRootAndCopyTemplates(hKey, (struct SEARCH_ROOT *)ItemPtr, v8) )
      {
        v11 = (const unsigned __int16 *)*((_QWORD *)ItemPtr + 1);
        v12 = 0;
        if ( CAddRemoveSynchronizer::Create(v8, 0, v11, &v12) >= 0 )
        {
          QueueWorkItem(
            (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))CreateLocationsForSearchRootWorker,
            v12);
          (*(void (__fastcall **)(struct CAddRemoveSynchronizer *))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      ++i;
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180022b78  mov     r11, rsp
0x180022b7b  mov     [r11+8], rbx
0x180022b7f  push    rbp
0x180022b80  push    rsi
0x180022b81  push    rdi
0x180022b82  push    r12
0x180022b84  push    r13
0x180022b86  push    r14
0x180022b88  push    r15
0x180022b8a  sub     rsp, 50h
0x180022b8e  xor     r13d, r13d
0x180022b91  lea     rax, [r11+20h]
0x180022b95  mov     [r11-48h], r13
0x180022b99  mov     r15, rdx
0x180022b9c  mov     [r11-50h], rax
0x180022ba0  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows Search\\Pr"...
0x180022ba7  mov     [r11-58h], r13
0x180022bab  mov     r12, rcx
0x180022bae  mov     [rsp+88h+samDesired], 20006h; samDesired
0x180022bb6  xor     r9d, r9d; lpClass
0x180022bb9  xor     r8d, r8d; Reserved
0x180022bbc  mov     [r11-68h], r13d
0x180022bc0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180022bc7  mov     [r11+20h], r13
0x180022bcb  call    cs:__imp_RegCreateKeyExW
0x180022bd1  test    eax, eax
0x180022bd3  jnz     loc_180022CA1
0x180022bd9  mov     rax, [r12]
0x180022bdd  test    rax, rax
0x180022be0  jz      short loc_180022BE6
0x180022be2  mov     esi, [rax]
0x180022be4  jmp     short loc_180022BE9
0x180022be6  mov     esi, r13d
0x180022be9  mov     r14, [r15+8]
0x180022bed  mov     rdi, r13
0x180022bf0  mov     ebx, r13d
0x180022bf3  mov     ebp, r13d
0x180022bf6  test    esi, esi
0x180022bf8  jle     loc_180022C93
0x180022bfe  cmp     rdi, r14
0x180022c01  jnb     short loc_180022C15
0x180022c03  mov     rax, [r15]
0x180022c06  cmp     ebx, [rax+rdi*4]
0x180022c09  jnz     short loc_180022C15
0x180022c0b  inc     ebx
0x180022c0d  inc     rdi
0x180022c10  cmp     rdi, r14
0x180022c13  jb      short loc_180022C06
0x180022c15  mov     rcx, [r12]; hdsa
0x180022c19  mov     edx, ebp; i
0x180022c1b  call    DSA_GetItemPtr
0x180022c20  mov     rcx, [rsp+88h+hKey]; hKey
0x180022c28  mov     r8d, ebx; int
0x180022c2b  mov     rdx, rax; struct SEARCH_ROOT *
0x180022c2e  mov     r13, rax
0x180022c31  call    ?ValidateSearchRootAndCopyTemplates@@YAJPEAUHKEY__@@PEAUSEARCH_ROOT@@H@Z; ValidateSearchRootAndCopyTemplates(HKEY__ *,SEARCH_ROOT *,int)
0x180022c36  test    eax, eax
0x180022c38  jnz     short loc_180022C87
0x180022c3a  mov     r8, [r13+8]; unsigned __int16 *
0x180022c3e  lea     r9, [rsp+88h+arg_10]; struct CAddRemoveSynchronizer **
0x180022c46  xor     edx, edx; int
0x180022c48  mov     [rsp+88h+arg_10], 0
0x180022c54  mov     ecx, ebx; int
0x180022c56  call    ?Create@CAddRemoveSynchronizer@@SAJHHPEBGPEAPEAV1@@Z; CAddRemoveSynchronizer::Create(int,int,ushort const *,CAddRemoveSynchronizer * *)
0x180022c5b  test    eax, eax
0x180022c5d  js      short loc_180022C87
0x180022c5f  mov     rdx, [rsp+88h+arg_10]; struct CAddRemoveSynchronizer *
0x180022c67  lea     rcx, ?CreateLocationsForSearchRootWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x180022c6e  call    ?QueueWorkItem@@YAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@ZPEAVCAddRemoveSynchronizer@@@Z; QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),CAddRemoveSynchronizer *)
0x180022c73  mov     rcx, [rsp+88h+arg_10]
0x180022c7b  mov     rax, [rcx]
0x180022c7e  mov     rax, [rax+10h]
0x180022c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c87  inc     ebp
0x180022c89  inc     ebx
0x180022c8b  cmp     ebp, esi
0x180022c8d  jl      loc_180022BFE
0x180022c93  mov     rcx, [rsp+88h+hKey]; hKey
0x180022c9b  call    cs:__imp_RegCloseKey
0x180022ca1  mov     rbx, [rsp+88h+arg_0]
0x180022ca9  add     rsp, 50h
0x180022cad  pop     r15
0x180022caf  pop     r14
0x180022cb1  pop     r13
0x180022cb3  pop     r12
0x180022cb5  pop     rdi
0x180022cb6  pop     rsi
0x180022cb7  pop     rbp
0x180022cb8  retn
```
