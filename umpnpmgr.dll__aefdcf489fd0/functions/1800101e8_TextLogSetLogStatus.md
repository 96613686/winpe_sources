# TextLogSetLogStatus

- ea: `0x1800101e8`
- end: `0x18001037d`
- name: `TextLogSetLogStatus`
- size: `405`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`
- `0x18000b360`
- `0x1800177e0`

## callees

- `0x18000bb04`
- `0x1800101d8`
- `0x1800101e8`
- `0x1800180b0`
- `0x18001812c`
- `0x1800182e4`

## import_xrefs

- `msvcrt!wcschr` at `0x180010272`
- `msvcrt!wcschr` at `0x180010272`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010318`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010318`

## pseudocode

```c
__int64 __fastcall TextLogSetLogStatus(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  unsigned int v5; // r14d
  int v6; // esi
  __int64 v7; // rax
  void *v8; // rbp
  const wchar_t *v9; // rbx
  const WCHAR *v10; // rsi
  wchar_t *v11; // rax
  __int64 v12; // r8
  int v13; // eax
  __int64 v15; // [rsp+28h] [rbp-50h]
  __int64 v16; // [rsp+28h] [rbp-50h]
  HANDLE KeyHandle; // [rsp+90h] [rbp+18h] BYREF
  __int64 v18; // [rsp+98h] [rbp+20h] BYREF

  v18 = 0;
  v4 = -2147483646;
  KeyHandle = 0;
  v5 = 0;
  v6 = pSetupCreateKeyWorker((void *)0xFFFFFFFF80000002LL, L"SYSTEM\\Setup\\SetupapiLogStatus", a3, 1u, 2u, v15, &v18);
  if ( v6 != 2 )
  {
    v4 = v18;
    goto LABEL_20;
  }
  v7 = pSetupDuplicateString(L"SYSTEM\\Setup\\SetupapiLogStatus");
  v8 = (void *)v7;
  if ( v7 )
  {
    v9 = (const wchar_t *)v7;
    while ( 1 )
    {
      v10 = v9;
      v11 = wcschr(v9, 0x5Cu);
      v9 = v11;
      if ( !v11 )
        goto LABEL_9;
      *v11 = 0;
      do
        ++v9;
      while ( *v9 == 92 );
      if ( !*v9 )
        break;
      if ( !v9 )
        goto LABEL_9;
      v13 = pSetupCreateKeyWorker((void *)v4, v10, v12, 0, 4u, v16, &KeyHandle);
LABEL_10:
      v6 = v13;
      if ( v4 != -2147483646 )
        pSetupCloseKey(v4);
      if ( v6 )
      {
        v4 = v18;
LABEL_18:
        HeapFree(hHeap, 0, v8);
LABEL_20:
        if ( !v6 )
        {
          pSetupGetFileTitle(*(unsigned __int16 **)(a1 + 16));
          LOBYTE(v5) = (unsigned int)pSetupSetValue((HANDLE)v4, 4u) == 0;
          pSetupCloseKey(v4);
        }
        return v5;
      }
      v4 = (__int64)KeyHandle;
      if ( !v9 )
        goto LABEL_18;
    }
    v9 = 0;
LABEL_9:
    v13 = pSetupCreateKeyWorker((void *)v4, v10, v12, 1u, 2u, v16, &KeyHandle);
    goto LABEL_10;
  }
  return v5;
}

```

## disassembly

```asm
0x1800101e8  mov     rax, rsp
0x1800101eb  mov     [rax+8], rbx
0x1800101ef  mov     [rax+10h], edx
0x1800101f2  push    rbp
0x1800101f3  push    rsi
0x1800101f4  push    rdi
0x1800101f5  push    r12
0x1800101f7  push    r13
0x1800101f9  push    r14
0x1800101fb  push    r15
0x1800101fd  sub     rsp, 40h
0x180010201  xor     r12d, r12d
0x180010204  mov     r15, rcx
0x180010207  mov     [rax+20h], r12
0x18001020b  mov     rdi, 0FFFFFFFF80000002h
0x180010212  mov     [rax+18h], r12
0x180010216  lea     rax, [rax+20h]
0x18001021a  mov     [rsp+78h+var_48], rax
0x18001021f  lea     rdx, aSystemSetupSet_0; "SYSTEM\\Setup\\SetupapiLogStatus"
0x180010226  lea     r9d, [r12+1]
0x18001022b  mov     [rsp+78h+var_58], 2
0x180010233  mov     rcx, rdi
0x180010236  mov     r14d, r12d
0x180010239  call    pSetupCreateKeyWorker
0x18001023e  mov     esi, eax
0x180010240  cmp     eax, 2
0x180010243  jnz     loc_180010320
0x180010249  lea     rcx, aSystemSetupSet_0; "SYSTEM\\Setup\\SetupapiLogStatus"
0x180010250  call    pSetupDuplicateString
0x180010255  mov     rbp, rax
0x180010258  test    rax, rax
0x18001025b  jz      loc_180010362
0x180010261  mov     rbx, rax
0x180010264  lea     r13d, [r12+5Ch]
0x180010269  mov     edx, r13d; Ch
0x18001026c  mov     rcx, rbx; Str
0x18001026f  mov     rsi, rbx
0x180010272  call    cs:__imp_wcschr
0x180010278  mov     rbx, rax
0x18001027b  test    rax, rax
0x18001027e  jz      short loc_180010299
0x180010280  mov     [rax], r12w
0x180010284  add     rbx, 2
0x180010288  movzx   eax, word ptr [rbx]
0x18001028b  cmp     ax, r13w
0x18001028f  jz      short loc_180010284
0x180010291  test    ax, ax
0x180010294  jnz     short loc_1800102E5
0x180010296  mov     rbx, r12
0x180010299  lea     rax, [rsp+78h+KeyHandle]
0x1800102a1  mov     r9d, 1
0x1800102a7  mov     [rsp+78h+var_48], rax
0x1800102ac  mov     [rsp+78h+var_58], 2
0x1800102b4  mov     rdx, rsi
0x1800102b7  mov     rcx, rdi
0x1800102ba  call    pSetupCreateKeyWorker
0x1800102bf  mov     esi, eax
0x1800102c1  cmp     rdi, 0FFFFFFFF80000002h
0x1800102c8  jz      short loc_1800102D2
0x1800102ca  mov     rcx, rdi
0x1800102cd  call    pSetupCloseKey
0x1800102d2  test    esi, esi
0x1800102d4  jnz     short loc_180010304
0x1800102d6  mov     rdi, [rsp+78h+KeyHandle]
0x1800102de  test    rbx, rbx
0x1800102e1  jnz     short loc_180010269
0x1800102e3  jmp     short loc_18001030C
0x1800102e5  test    rbx, rbx
0x1800102e8  jz      short loc_180010299
0x1800102ea  lea     rax, [rsp+78h+KeyHandle]
0x1800102f2  xor     r9d, r9d
0x1800102f5  mov     [rsp+78h+var_48], rax
0x1800102fa  mov     [rsp+78h+var_58], 4
0x180010302  jmp     short loc_1800102B4
0x180010304  mov     rdi, [rsp+78h+arg_18]
0x18001030c  mov     rcx, cs:hHeap; hHeap
0x180010313  mov     r8, rbp; lpMem
0x180010316  xor     edx, edx; dwFlags
0x180010318  call    cs:__imp_HeapFree
0x18001031e  jmp     short loc_180010328
0x180010320  mov     rdi, [rsp+78h+arg_18]
0x180010328  test    esi, esi
0x18001032a  jnz     short loc_180010362
0x18001032c  mov     rcx, [r15+10h]
0x180010330  call    pSetupGetFileTitle
0x180010335  mov     rdx, rax
0x180010338  mov     [rsp+78h+var_58], 4; ULONG
0x180010340  mov     rcx, rdi; KeyHandle
0x180010343  lea     r9, [rsp+78h+arg_8]
0x18001034b  lea     r8d, [rsi+4]
0x18001034f  call    pSetupSetValue
0x180010354  test    eax, eax
0x180010356  mov     rcx, rdi
0x180010359  setz    r14b
0x18001035d  call    pSetupCloseKey
0x180010362  mov     rbx, [rsp+78h+arg_0]
0x18001036a  mov     eax, r14d
0x18001036d  add     rsp, 40h
0x180010371  pop     r15
0x180010373  pop     r14
0x180010375  pop     r13
0x180010377  pop     r12
0x180010379  pop     rdi
0x18001037a  pop     rsi
0x18001037b  pop     rbp
0x18001037c  retn
```
