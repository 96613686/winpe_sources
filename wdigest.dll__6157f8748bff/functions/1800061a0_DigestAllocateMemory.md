# DigestAllocateMemory

- ea: `0x1800061a0`
- end: `0x180006259`
- name: `DigestAllocateMemory`
- size: `185`
- prototype: `__int64 __fastcall(size_t Size)`
- caller_count: `49`
- callee_count: `4`
- tags: ``

## callers

- `0x180001bb0`
- `0x180002ef0`
- `0x180003a50`
- `0x180004cb0`
- `0x180006260`
- `0x1800076b0`
- `0x180007aa0`
- `0x180009820`
- `0x18000c4c0`
- `0x18000cca0`
- `0x18000f3dc`
- `0x180010510`
- `0x18001721c`
- `0x1800179f4`
- `0x1800192e8`
- `0x1800195dc`
- `0x180019bd0`
- `0x18001ad3c`
- `0x18001b2f8`
- `0x18001b4b0`
- `0x18001bcec`
- `0x18001bf40`
- `0x18001c8e0`
- `0x18001d5e8`
- `0x18001e218`
- `0x18001e4b0`
- `0x1800206d0`
- `0x180023f80`
- `0x180024ea0`
- `0x180026020`
- `0x180026970`
- `0x1800277a0`
- `0x180027e2c`
- `0x1800283d8`
- `0x180028ef4`
- `0x180029c98`
- `0x18002a6f8`
- `0x18002ac54`
- `0x18002b2b8`
- `0x18002ba20`
- `0x18002bd34`
- `0x180030628`
- `0x180031080`
- `0x1800328a0`
- `0x1800332dc`
- `0x180033368`
- `0x180033500`
- `0x180033564`
- `0x180033680`

## callees

- `0x1800061a0`
- `0x180013304`
- `0x180032ec8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000620e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000620e`

## pseudocode

```c
HLOCAL __fastcall DigestAllocateMemory(size_t Size)
{
  unsigned int v1; // ebx
  void *v2; // rax
  HLOCAL v3; // rdi
  _QWORD *v4; // rcx
  __int64 v6; // rdx

  v1 = Size;
  if ( g_NtDigestState != 1 )
  {
    v3 = LocalAlloc(0x40u, (unsigned int)Size);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      return v3;
    v6 = 29;
LABEL_10:
    WPP_SF_Lq(v4[2], v6, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v1, v3);
    return v3;
  }
  v2 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)&g_LsaFunctions + 40LL))((unsigned int)Size);
  v3 = v2;
  if ( v2 )
    memset_0(v2, 0, v1);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v6 = 28;
    goto LABEL_10;
  }
  return v3;
}

```

## disassembly

```asm
0x1800061a0  mov     [rsp+arg_0], rbx
0x1800061a5  push    rdi
0x1800061a6  sub     rsp, 30h
0x1800061aa  cmp     cs:g_NtDigestState, 1
0x1800061b1  mov     ebx, ecx
0x1800061b3  jnz     short loc_180006206
0x1800061b5  mov     rax, cs:g_LsaFunctions
0x1800061bc  mov     ecx, ebx
0x1800061be  mov     rax, [rax+28h]
0x1800061c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c7  mov     rdi, rax
0x1800061ca  test    rax, rax
0x1800061cd  jz      short loc_1800061DC
0x1800061cf  mov     r8d, ebx; Size
0x1800061d2  xor     edx, edx; Val
0x1800061d4  mov     rcx, rax; void *
0x1800061d7  call    memset_0
0x1800061dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061e3  lea     rax, WPP_GLOBAL_Control
0x1800061ea  cmp     rcx, rax
0x1800061ed  jz      short loc_1800061F8
0x1800061ef  test    dword ptr [rcx+1Ch], 100h
0x1800061f6  jnz     short loc_180006252
0x1800061f8  mov     rbx, [rsp+38h+arg_0]
0x1800061fd  mov     rax, rdi
0x180006200  add     rsp, 30h
0x180006204  pop     rdi
0x180006205  retn
0x180006206  mov     rdx, rbx; uBytes
0x180006209  mov     ecx, 40h ; '@'; uFlags
0x18000620e  call    cs:__imp_LocalAlloc
0x180006214  mov     rdi, rax
0x180006217  mov     rcx, cs:WPP_GLOBAL_Control
0x18000621e  lea     rax, WPP_GLOBAL_Control
0x180006225  cmp     rcx, rax
0x180006228  jz      short loc_1800061F8
0x18000622a  test    dword ptr [rcx+1Ch], 100h
0x180006231  jz      short loc_1800061F8
0x180006233  mov     edx, 1Dh
0x180006238  mov     rcx, [rcx+10h]
0x18000623c  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180006243  mov     r9d, ebx
0x180006246  mov     [rsp+38h+var_18], rdi
0x18000624b  call    WPP_SF_Lq
0x180006250  jmp     short loc_1800061F8
0x180006252  mov     edx, 1Ch
0x180006257  jmp     short loc_180006238
```
