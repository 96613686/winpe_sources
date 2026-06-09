# CASFLonghandObject::Restore(CASFArchive &)

- ea: `0x180022980`
- end: `0x180022a2b`
- name: `?Restore@CASFLonghandObject@@UEAAJAEAVCASFArchive@@@Z`
- size: `171`
- prototype: `int(CASFLonghandObject *__hidden this, struct CASFArchive *)`
- caller_count: `34`
- callee_count: `4`
- tags: ``

## callers

- `0x180012080`
- `0x1800209d0`
- `0x180020d20`
- `0x180020e70`
- `0x180021130`
- `0x1800212d0`
- `0x180021350`
- `0x180021570`
- `0x1800218c0`
- `0x180021b30`
- `0x180021c20`
- `0x180021cf0`
- `0x180021da0`
- `0x180021e90`
- `0x180021f80`
- `0x180022220`
- `0x180022350`
- `0x1800224f0`
- `0x180022590`
- `0x180022700`
- `0x180022890`
- `0x180022b30`
- `0x180022d80`
- `0x180022eb0`
- `0x180022f60`
- `0x1800230f0`
- `0x180023460`
- `0x180023570`
- `0x180023760`
- `0x180023c40`
- `0x180023ce0`
- `0x180023e50`
- `0x180024120`
- `0x180028630`

## callees

- `0x18001d39c`
- `0x18001d424`
- `0x180022980`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CASFLonghandObject::Restore(CASFLonghandObject *this, struct CASFArchive *a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 v4; // rdi
  __int64 result; // rax
  unsigned int v7; // ebx
  unsigned int v8; // edi
  unsigned __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((_QWORD *)a2 + 1);
  v4 = *(_QWORD *)a2;
  v9 = (unsigned int)(*((_DWORD *)a2 + 4) - v2);
  result = CASFArchive::LoadGUID(a2, (struct _GUID *)this + 1, &v9);
  if ( (int)result >= 0 )
  {
    result = CASFArchive::LoadQWORD(a2, (unsigned __int64 *)this + 4, &v9);
    if ( (int)result >= 0 )
    {
      if ( *((_QWORD *)this + 4) >= 0x18u )
      {
        if ( v4 > v2 || (__int64)(v2 - v4) > 0xFFFFFFFFLL )
        {
          return 2147942487LL;
        }
        else
        {
          v7 = v2 - v4;
          v8 = *((_DWORD *)a2 + 4) - *(_DWORD *)a2;
          if ( v7 >= v8
            || v8 - v7 < (unsigned __int64)(*(__int64 (__fastcall **)(CASFLonghandObject *))(*(_QWORD *)this + 32LL))(this) )
          {
            return 3222079441LL;
          }
          else
          {
            return 0;
          }
        }
      }
      else
      {
        return 3222079458LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180022980  push    rbx
0x180022982  push    rsi
0x180022983  push    rdi
0x180022984  push    r14
0x180022986  sub     rsp, 28h
0x18002298a  mov     eax, [rdx+10h]
0x18002298d  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x180022992  mov     rbx, [rdx+8]
0x180022996  mov     rsi, rdx
0x180022999  mov     rdi, [rdx]
0x18002299c  sub     eax, ebx
0x18002299e  mov     r14, rcx
0x1800229a1  mov     [rsp+48h+arg_0], rax
0x1800229a6  lea     rdx, [rcx+10h]; struct _GUID *
0x1800229aa  mov     rcx, rsi; this
0x1800229ad  call    ?LoadGUID@CASFArchive@@QEAAJAEAU_GUID@@PEA_K@Z; CASFArchive::LoadGUID(_GUID &,unsigned __int64 *)
0x1800229b2  test    eax, eax
0x1800229b4  js      short loc_180022A21
0x1800229b6  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x1800229bb  mov     rcx, rsi; this
0x1800229be  lea     rdx, [r14+20h]; unsigned __int64 *
0x1800229c2  call    ?LoadQWORD@CASFArchive@@QEAAJAEA_KPEA_K@Z; CASFArchive::LoadQWORD(unsigned __int64 &,unsigned __int64 *)
0x1800229c7  test    eax, eax
0x1800229c9  js      short loc_180022A21
0x1800229cb  cmp     qword ptr [r14+20h], 18h
0x1800229d0  jnb     short loc_1800229D9
0x1800229d2  mov     eax, 0C00D07E2h
0x1800229d7  jmp     short loc_180022A21
0x1800229d9  cmp     rdi, rbx
0x1800229dc  ja      short loc_180022A1C
0x1800229de  mov     rax, rbx
0x1800229e1  mov     ecx, 0FFFFFFFFh
0x1800229e6  sub     rax, rdi
0x1800229e9  cmp     rax, rcx
0x1800229ec  jg      short loc_180022A1C
0x1800229ee  sub     ebx, edi
0x1800229f0  mov     edi, [rsi+10h]
0x1800229f3  sub     edi, [rsi]
0x1800229f5  cmp     ebx, edi
0x1800229f7  jb      short loc_180022A00
0x1800229f9  mov     eax, 0C00D07D1h
0x1800229fe  jmp     short loc_180022A21
0x180022a00  mov     rax, [r14]
0x180022a03  mov     rcx, r14
0x180022a06  mov     rax, [rax+20h]
0x180022a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a0f  sub     edi, ebx
0x180022a11  mov     ecx, edi
0x180022a13  cmp     rcx, rax
0x180022a16  jb      short loc_1800229F9
0x180022a18  xor     eax, eax
0x180022a1a  jmp     short loc_180022A21
0x180022a1c  mov     eax, 80070057h
0x180022a21  add     rsp, 28h
0x180022a25  pop     r14
0x180022a27  pop     rdi
0x180022a28  pop     rsi
0x180022a29  pop     rbx
0x180022a2a  retn
```
