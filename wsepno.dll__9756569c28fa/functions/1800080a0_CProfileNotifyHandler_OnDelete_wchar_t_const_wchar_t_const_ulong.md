# CProfileNotifyHandler::OnDelete(wchar_t const *,wchar_t const *,ulong)

- ea: `0x1800080a0`
- end: `0x1800081bd`
- name: `?OnDelete@CProfileNotifyHandler@@UEAAJPEB_W0K@Z`
- size: `285`
- prototype: `__int64 __fastcall(CProfileNotifyHandler *this, const wchar_t *, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180001b78`
- `0x180003ab8`
- `0x180003be0`
- `0x1800080a0`
- `0x180008648`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall CProfileNotifyHandler::OnDelete(
        CProfileNotifyHandler *this,
        const wchar_t *a2,
        const wchar_t *a3,
        int a4)
{
  signed int StringCopy; // edi
  char *v8; // rax
  void *v9; // rdx
  unsigned int v10; // r8d
  wchar_t **v11; // rbx
  void **v12; // rsi
  wchar_t *v13; // rcx
  void *v14; // rdx
  __int64 result; // rax

  StringCopy = -2147024882;
  v8 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = (wchar_t **)v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &CProfileTask_OnDelete::`vftable';
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 0;
    if ( a2 && a3 )
    {
      v12 = (void **)(v8 + 16);
      StringCopy = ProfNotif_CreateStringCopy(a2, (wchar_t **)v8 + 2);
      if ( StringCopy >= 0 )
      {
        StringCopy = ProfNotif_CreateStringCopy(a3, v11 + 3);
        if ( StringCopy >= 0 )
        {
          *((_DWORD *)v11 + 2) = a4;
          StringCopy = (*((__int64 (__fastcall **)(wchar_t **))*v11 + 1))(v11);
LABEL_10:
          (*(void (__fastcall **)(wchar_t **, __int64))*v11)(v11, 1);
          if ( StringCopy >= 0 || StringCopy == -2147213053 )
            goto LABEL_13;
          goto LABEL_12;
        }
      }
    }
    else
    {
      StringCopy = -2147418113;
      v12 = (void **)(v8 + 16);
    }
    ProfNotif_HeapFree(*v12, v9);
    v13 = v11[3];
    *v12 = 0;
    ProfNotif_HeapFree(v13, v14);
    v11[3] = 0;
    goto LABEL_10;
  }
LABEL_12:
  Profile_LogDeleteFailure(StringCopy, a2, v10);
LABEL_13:
  result = 0;
  if ( StringCopy != -2147213053 )
    return (unsigned int)StringCopy;
  return result;
}

```

## disassembly

```asm
0x1800080a0  push    rbx
0x1800080a2  push    rbp
0x1800080a3  push    rsi
0x1800080a4  push    rdi
0x1800080a5  push    r14
0x1800080a7  push    r15
0x1800080a9  sub     rsp, 38h
0x1800080ad  mov     rbp, rdx
0x1800080b0  mov     ecx, 20h ; ' '; unsigned __int64
0x1800080b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800080bc  mov     r15d, r9d
0x1800080bf  mov     r14, r8
0x1800080c2  mov     edi, 8007000Eh
0x1800080c7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800080cc  mov     [rsp+68h+var_48], rax
0x1800080d1  mov     rbx, rax
0x1800080d4  test    rax, rax
0x1800080d7  jz      loc_18000819B
0x1800080dd  mov     dword ptr [rbx+8], 0
0x1800080e4  lea     rax, ??_7CProfileTask_OnDelete@@6B@; const CProfileTask_OnDelete::`vftable'
0x1800080eb  mov     [rbx], rax
0x1800080ee  mov     qword ptr [rbx+10h], 0
0x1800080f6  mov     qword ptr [rbx+18h], 0
0x1800080fe  test    rbx, rbx
0x180008101  jz      loc_18000819B
0x180008107  test    rbp, rbp
0x18000810a  jz      short loc_18000813E
0x18000810c  test    r14, r14
0x18000810f  jz      short loc_18000813E
0x180008111  lea     rsi, [rbx+10h]
0x180008115  mov     rcx, rbp; wchar_t *
0x180008118  mov     rdx, rsi; wchar_t **
0x18000811b  call    ?ProfNotif_CreateStringCopy@@YAJPEB_WPEAPEA_W@Z; ProfNotif_CreateStringCopy(wchar_t const *,wchar_t * *)
0x180008120  mov     edi, eax
0x180008122  test    eax, eax
0x180008124  js      short loc_180008147
0x180008126  lea     rdx, [rbx+18h]; wchar_t **
0x18000812a  mov     rcx, r14; wchar_t *
0x18000812d  call    ?ProfNotif_CreateStringCopy@@YAJPEB_WPEAPEA_W@Z; ProfNotif_CreateStringCopy(wchar_t const *,wchar_t * *)
0x180008132  mov     edi, eax
0x180008134  test    eax, eax
0x180008136  js      short loc_180008147
0x180008138  mov     [rbx+8], r15d
0x18000813c  jmp     short loc_18000816B
0x18000813e  mov     edi, 8000FFFFh
0x180008143  lea     rsi, [rbx+10h]
0x180008147  mov     rcx, [rsi]; lpMem
0x18000814a  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000814f  mov     rcx, [rbx+18h]; lpMem
0x180008153  mov     qword ptr [rsi], 0
0x18000815a  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000815f  mov     qword ptr [rbx+18h], 0
0x180008167  test    edi, edi
0x180008169  js      short loc_18000817C
0x18000816b  mov     rax, [rbx]
0x18000816e  mov     rcx, rbx
0x180008171  mov     rax, [rax+8]
0x180008175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000817a  mov     edi, eax
0x18000817c  mov     rax, [rbx]
0x18000817f  mov     edx, 1
0x180008184  mov     rcx, rbx
0x180008187  mov     rax, [rax]
0x18000818a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000818f  test    edi, edi
0x180008191  jns     short loc_1800081A5
0x180008193  cmp     edi, 80042103h
0x180008199  jz      short loc_1800081A5
0x18000819b  mov     rdx, rbp; wchar_t *
0x18000819e  mov     ecx, edi; dwMessageId
0x1800081a0  call    ?Profile_LogDeleteFailure@@YAXJPEB_WK@Z; Profile_LogDeleteFailure(long,wchar_t const *,ulong)
0x1800081a5  xor     eax, eax
0x1800081a7  cmp     edi, 80042103h
0x1800081ad  cmovnz  eax, edi
0x1800081b0  add     rsp, 38h
0x1800081b4  pop     r15
0x1800081b6  pop     r14
0x1800081b8  pop     rdi
0x1800081b9  pop     rsi
0x1800081ba  pop     rbp
0x1800081bb  pop     rbx
0x1800081bc  retn
```
