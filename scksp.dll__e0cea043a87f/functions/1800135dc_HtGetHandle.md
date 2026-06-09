# HtGetHandle

- ea: `0x1800135dc`
- end: `0x18001372b`
- name: `HtGetHandle`
- size: `335`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `26`
- callee_count: `5`
- tags: ``

## callers

- `0x180015a5c`
- `0x180018dc0`
- `0x18001c818`
- `0x18001d030`
- `0x18001d4e0`
- `0x18001dbc8`
- `0x18001e590`
- `0x18001e92c`
- `0x18001ee70`
- `0x18001f2f0`
- `0x18001f61c`
- `0x1800203a0`
- `0x1800206e8`
- `0x180020ed4`
- `0x180021220`
- `0x1800229fc`
- `0x1800232ec`
- `0x180023dd0`
- `0x180024250`
- `0x1800253c0`
- `0x180025ff0`
- `0x180027054`
- `0x1800283dc`
- `0x180028a30`
- `0x180029abc`
- `0x18002a4c0`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x1800135dc`
- `0x18003af5c`
- `0x18003afc0`

## pseudocode

```c
__int64 __fastcall HtGetHandle(__int64 a1, int a2, _QWORD *a3)
{
  int v5; // esi
  LPVOID v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax

  v5 = a1;
  if ( a3 )
  {
    v7 = KspEnterCriticalSection(&CriticalSection);
    if ( v7 )
    {
      WppTraceIndent((__int64)v6, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids,
          (_DWORD)WPP_pszIndent,
          v7);
      }
    }
    else
    {
      v8 = (unsigned int)(v5 - 370672441);
      if ( (unsigned int)v8 < HIDWORD(qword_18004C048)
        && (v6 = g_HandleTable, v9 = 2 * v8, *((_DWORD *)g_HandleTable + 2 * v9) == a2) )
      {
        *a3 = *((_QWORD *)g_HandleTable + v9 + 1);
      }
      else
      {
        WppTraceIndent((__int64)v6, 2u);
        v7 = -2146435068;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids,
            (_DWORD)WPP_pszIndent,
            4);
        }
      }
      KspLeaveCriticalSection(&CriticalSection);
    }
  }
  else
  {
    WppTraceIndent(a1, 2u);
    v7 = -2146435068;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids,
        (_DWORD)WPP_pszIndent,
        4);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800135dc  push    rbx
0x1800135de  push    rbp
0x1800135df  push    rsi
0x1800135e0  push    rdi
0x1800135e1  sub     rsp, 38h
0x1800135e5  mov     rdi, r8
0x1800135e8  mov     ebp, edx
0x1800135ea  mov     rsi, rcx
0x1800135ed  test    r8, r8
0x1800135f0  jz      loc_1800136D0
0x1800135f6  lea     rcx, CriticalSection
0x1800135fd  call    KspEnterCriticalSection
0x180013602  mov     ebx, eax
0x180013604  test    eax, eax
0x180013606  jz      short loc_18001364B
0x180013608  mov     edx, 2
0x18001360d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013612  mov     rcx, cs:WPP_GLOBAL_Control
0x180013619  lea     rdx, WPP_GLOBAL_Control
0x180013620  cmp     rcx, rdx
0x180013623  jz      loc_180013720
0x180013629  test    byte ptr [rcx+1Ch], 1
0x18001362d  jz      loc_180013720
0x180013633  cmp     byte ptr [rcx+19h], 2
0x180013637  jb      loc_180013720
0x18001363d  mov     edx, 1Bh
0x180013642  mov     [rsp+58h+var_38], ebx
0x180013646  jmp     loc_180013709
0x18001364b  lea     eax, [rsi-16180339h]
0x180013651  cmp     eax, dword ptr cs:qword_18004C048+4
0x180013657  jnb     short loc_180013672
0x180013659  mov     rcx, cs:g_HandleTable
0x180013660  add     rax, rax
0x180013663  cmp     [rcx+rax*8], ebp
0x180013666  jnz     short loc_180013672
0x180013668  mov     rax, [rcx+rax*8+8]
0x18001366d  mov     [rdi], rax
0x180013670  jmp     short loc_1800136C2
0x180013672  mov     edx, 2
0x180013677  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001367c  mov     eax, 80100004h
0x180013681  mov     ebx, eax
0x180013683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001368a  lea     rdx, WPP_GLOBAL_Control
0x180013691  cmp     rcx, rdx
0x180013694  jz      short loc_1800136C2
0x180013696  test    byte ptr [rcx+1Ch], 1
0x18001369a  jz      short loc_1800136C2
0x18001369c  cmp     byte ptr [rcx+19h], 2
0x1800136a0  jb      short loc_1800136C2
0x1800136a2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800136a9  lea     r8, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids
0x1800136b0  mov     rcx, [rcx+10h]
0x1800136b4  mov     edx, 1Ch
0x1800136b9  mov     [rsp+58h+var_38], eax
0x1800136bd  call    WPP_SF_sd
0x1800136c2  lea     rcx, CriticalSection
0x1800136c9  call    KspLeaveCriticalSection
0x1800136ce  jmp     short loc_180013720
0x1800136d0  mov     edx, 2
0x1800136d5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800136da  mov     eax, 80100004h
0x1800136df  mov     ebx, eax
0x1800136e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136e8  lea     rdx, WPP_GLOBAL_Control
0x1800136ef  cmp     rcx, rdx
0x1800136f2  jz      short loc_180013720
0x1800136f4  test    byte ptr [rcx+1Ch], 1
0x1800136f8  jz      short loc_180013720
0x1800136fa  cmp     byte ptr [rcx+19h], 2
0x1800136fe  jb      short loc_180013720
0x180013700  mov     edx, 1Ah
0x180013705  mov     [rsp+58h+var_38], eax
0x180013709  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180013710  lea     r8, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids
0x180013717  mov     rcx, [rcx+10h]
0x18001371b  call    WPP_SF_sd
0x180013720  mov     eax, ebx
0x180013722  add     rsp, 38h
0x180013726  pop     rdi
0x180013727  pop     rsi
0x180013728  pop     rbp
0x180013729  pop     rbx
0x18001372a  retn
```
