# Storage::CVolumeInfo::_GetMountPointsInfo(ushort * *,ulong *)

- ea: `0x18002866c`
- end: `0x18002870d`
- name: `?_GetMountPointsInfo@CVolumeInfo@Storage@@AEAAJPEAPEAGPEAK@Z`
- size: `161`
- prototype: `__int64 __fastcall(Storage::CVolumeInfo *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, service_task`

## callers

- `0x180027970`
- `0x180027c70`

## callees

- `0x180007b04`
- `0x180007b20`
- `0x18002866c`
- `0x180032c52`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800286b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800286b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800286c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800286c1`

## pseudocode

```c
__int64 __fastcall Storage::CVolumeInfo::_GetMountPointsInfo(
        Storage::CVolumeInfo *this,
        unsigned __int16 **a2,
        unsigned int *a3)
{
  char *v3; // rsi
  int v7; // eax
  const void *v8; // r15
  size_t v9; // rbp
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v11; // rax
  unsigned int v12; // ebx

  v3 = (char *)this + 3416;
  *a3 = 0;
  *a2 = 0;
  CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter((char *)this + 3416);
  v7 = *((_DWORD *)this + 852);
  if ( v7 )
  {
    v8 = (const void *)*((_QWORD *)this + 425);
    v9 = (unsigned int)(2 * v7);
    ProcessHeap = GetProcessHeap();
    v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, (unsigned int)v9);
    *a2 = v11;
    if ( v11 )
    {
      memcpy_0(v11, v8, v9);
      v12 = 0;
      *a3 = *((_DWORD *)this + 852);
    }
    else
    {
      v12 = -2147024882;
    }
  }
  else
  {
    v12 = -2147467259;
  }
  CCritSectWithResource<CDummyResource>::Leave(v3);
  return v12;
}

```

## disassembly

```asm
0x18002866c  push    rbx
0x18002866e  push    rbp
0x18002866f  push    rsi
0x180028670  push    rdi
0x180028671  push    r14
0x180028673  push    r15
0x180028675  sub     rsp, 28h
0x180028679  lea     rsi, [rcx+0D58h]
0x180028680  mov     dword ptr [r8], 0
0x180028687  mov     rdi, rcx
0x18002868a  mov     qword ptr [rdx], 0
0x180028691  mov     rcx, rsi
0x180028694  mov     r14, r8
0x180028697  mov     rbx, rdx
0x18002869a  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x18002869f  mov     eax, [rdi+0D50h]
0x1800286a5  test    eax, eax
0x1800286a7  jz      short loc_1800286F1
0x1800286a9  mov     r15, [rdi+0D48h]
0x1800286b0  lea     ebp, [rax+rax]
0x1800286b3  call    cs:__imp_GetProcessHeap
0x1800286b9  mov     r8d, ebp; dwBytes
0x1800286bc  xor     edx, edx; dwFlags
0x1800286be  mov     rcx, rax; hHeap
0x1800286c1  call    cs:__imp_HeapAlloc
0x1800286c7  mov     [rbx], rax
0x1800286ca  test    rax, rax
0x1800286cd  jnz     short loc_1800286D6
0x1800286cf  mov     ebx, 8007000Eh
0x1800286d4  jmp     short loc_1800286F6
0x1800286d6  mov     r8, rbp; Size
0x1800286d9  mov     rdx, r15; Src
0x1800286dc  mov     rcx, rax; void *
0x1800286df  call    memcpy_0
0x1800286e4  mov     eax, [rdi+0D50h]
0x1800286ea  xor     ebx, ebx
0x1800286ec  mov     [r14], eax
0x1800286ef  jmp     short loc_1800286F6
0x1800286f1  mov     ebx, 80004005h
0x1800286f6  mov     rcx, rsi
0x1800286f9  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x1800286fe  mov     eax, ebx
0x180028700  add     rsp, 28h
0x180028704  pop     r15
0x180028706  pop     r14
0x180028708  pop     rdi
0x180028709  pop     rsi
0x18002870a  pop     rbp
0x18002870b  pop     rbx
0x18002870c  retn
```
