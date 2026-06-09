# SdbpOpenDatabaseInMemory

- ea: `0x140017730`
- end: `0x140017897`
- name: `SdbpOpenDatabaseInMemory`
- size: `359`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018e34`
- `0x140019018`

## callees

- `0x14001008c`
- `0x140013738`
- `0x140017730`
- `0x1400178a0`
- `0x140017be4`
- `0x140017cf4`
- `0x14002e420`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140017771`
- `ntdll!RtlAllocateHeap` at `0x140017771`
- `ntdll!RtlFreeHeap` at `0x1400177fe`
- `ntdll!RtlFreeHeap` at `0x1400177fe`

## string_xrefs

- `0x1400177d1`: `Can't read database header`
- `0x14001778c`: `SdbpOpenDatabaseInMemory`
- `0x1400177de`: `SdbpOpenDatabaseInMemory`
- `0x140017843`: `SdbpOpenDatabaseInMemory`
- `0x140017880`: `SdbpValidateAndApplyCompatFlags failed [%x]`

## pseudocode

```c
void *__fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2, unsigned int a3)
{
  _QWORD *Heap; // rax
  void *v7; // rbx
  int v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  int v13; // [rsp+38h] [rbp-40h]

  v12 = 0;
  v13 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v7 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2891, "Failed to allocate DB structure");
    return 0;
  }
  *((_DWORD *)Heap + 5) = a2;
  *((_DWORD *)Heap + 4) = 0;
  *((_DWORD *)Heap + 6) |= 1u;
  Heap[1] = a1;
  *Heap = 0;
  if ( !(unsigned int)SdbpReadMappedData(Heap, 0, &v12, 12) )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2902, "Can't read database header");
LABEL_5:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    return 0;
  }
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v9 = v13;
    if ( v13 != 1717724275 && (a3 & 2) == 0 )
    {
      v10 = "Magic does not match a valid value: [0x%lx]";
      v11 = 2908;
LABEL_11:
      AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", v11, v10, v9);
      goto LABEL_5;
    }
  }
  if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v12, a3) )
    goto LABEL_5;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v9 = SdbpValidateRootTagSizes(v7);
    if ( v9 < 0 )
    {
      v10 = "SdbpValidateAndApplyCompatFlags failed [%x]";
      v11 = 2920;
      goto LABEL_11;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140017730  push    rbx
0x140017732  push    rbp
0x140017733  push    rsi
0x140017734  push    rdi
0x140017735  sub     rsp, 58h
0x140017739  mov     rax, cs:__security_cookie
0x140017740  xor     rax, rsp
0x140017743  mov     [rsp+78h+var_38], rax
0x140017748  xor     eax, eax
0x14001774a  mov     rbp, rcx
0x14001774d  mov     rcx, gs:60h
0x140017756  mov     esi, r8d
0x140017759  mov     edi, edx
0x14001775b  mov     [rsp+78h+var_48], rax
0x140017760  mov     r8d, 0A80h; Size
0x140017766  mov     [rsp+78h+var_40], eax
0x14001776a  lea     edx, [rax+8]; Flags
0x14001776d  mov     rcx, [rcx+30h]; HeapHandle
0x140017771  call    cs:__imp_RtlAllocateHeap
0x140017777  mov     rbx, rax
0x14001777a  test    rax, rax
0x14001777d  jnz     short loc_14001779D
0x14001777f  lea     r9, aFailedToAlloca_8; "Failed to allocate DB structure"
0x140017786  mov     r8d, 0B4Bh
0x14001778c  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x140017793  lea     ecx, [rax+1]
0x140017796  call    AslLogCallPrintf
0x14001779b  jmp     short loc_140017804
0x14001779d  mov     [rax+14h], edi
0x1400177a0  lea     r8, [rsp+78h+var_48]
0x1400177a5  mov     edi, 1
0x1400177aa  mov     dword ptr [rax+10h], 0
0x1400177b1  or      [rax+18h], edi
0x1400177b4  xor     edx, edx
0x1400177b6  mov     rcx, rbx
0x1400177b9  mov     [rax+8], rbp
0x1400177bd  mov     qword ptr [rax], 0
0x1400177c4  lea     r9d, [rdi+0Bh]
0x1400177c8  call    SdbpReadMappedData
0x1400177cd  test    eax, eax
0x1400177cf  jnz     short loc_14001781C
0x1400177d1  lea     r9, aCanTReadDataba; "Can't read database header"
0x1400177d8  mov     r8d, 0B56h
0x1400177de  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x1400177e5  mov     ecx, edi
0x1400177e7  call    AslLogCallPrintf
0x1400177ec  mov     rcx, gs:60h
0x1400177f5  mov     r8, rbx; P
0x1400177f8  xor     edx, edx; Flags
0x1400177fa  mov     rcx, [rcx+30h]; HeapHandle
0x1400177fe  call    cs:__imp_RtlFreeHeap
0x140017804  xor     eax, eax
0x140017806  mov     rcx, [rsp+78h+var_38]
0x14001780b  xor     rcx, rsp; StackCookie
0x14001780e  call    __security_check_cookie
0x140017813  add     rsp, 58h
0x140017817  pop     rdi
0x140017818  pop     rsi
0x140017819  pop     rbp
0x14001781a  pop     rbx
0x14001781b  retn
0x14001781c  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x140017821  test    eax, eax
0x140017823  jz      short loc_140017857
0x140017825  mov     eax, [rsp+78h+var_40]
0x140017829  cmp     eax, 66626473h
0x14001782e  jz      short loc_140017857
0x140017830  test    sil, 2
0x140017834  jnz     short loc_140017857
0x140017836  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x14001783d  mov     r8d, 0B5Ch
0x140017843  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x14001784a  mov     [rsp+78h+var_58], eax
0x14001784e  mov     ecx, edi
0x140017850  call    AslLogCallPrintf
0x140017855  jmp     short loc_1400177EC
0x140017857  mov     r8d, esi
0x14001785a  lea     rdx, [rsp+78h+var_48]
0x14001785f  mov     rcx, rbx
0x140017862  call    SdbpValidateAndApplyCompatFlags
0x140017867  test    eax, eax
0x140017869  jz      short loc_1400177EC
0x14001786b  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x140017870  test    eax, eax
0x140017872  jz      short loc_14001788F
0x140017874  mov     rcx, rbx
0x140017877  call    SdbpValidateRootTagSizes
0x14001787c  test    eax, eax
0x14001787e  jns     short loc_14001788F
0x140017880  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x140017887  mov     r8d, 0B68h
0x14001788d  jmp     short loc_140017843
0x14001788f  mov     rax, rbx
0x140017892  jmp     loc_140017806
```
