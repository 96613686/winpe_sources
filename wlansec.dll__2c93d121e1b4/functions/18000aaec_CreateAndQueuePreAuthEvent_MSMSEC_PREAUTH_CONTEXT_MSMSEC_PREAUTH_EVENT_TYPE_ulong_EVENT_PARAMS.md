# CreateAndQueuePreAuthEvent(MSMSEC_PREAUTH_CONTEXT *,MSMSEC_PREAUTH_EVENT_TYPE,ulong,EVENT_PARAMS *)

- ea: `0x18000aaec`
- end: `0x18000acf3`
- name: `?CreateAndQueuePreAuthEvent@@YAKPEAUMSMSEC_PREAUTH_CONTEXT@@W4MSMSEC_PREAUTH_EVENT_TYPE@@KPEAUEVENT_PARAMS@@@Z`
- size: `519`
- prototype: ``
- caller_count: `13`
- callee_count: `6`
- tags: ``

## callers

- `0x1800038e4`
- `0x180006b34`
- `0x180008be4`
- `0x1800092dc`
- `0x1800096b8`
- `0x180009d70`
- `0x180067f80`
- `0x180068050`
- `0x1800683c0`
- `0x1800685d0`
- `0x180068950`
- `0x180068c50`
- `0x18006a310`

## callees

- `0x1800063b0`
- `0x18000892c`
- `0x180008998`
- `0x18000aaec`
- `0x18000b2c0`
- `0x18000e620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab43`

## pseudocode

```c
__int64 __fastcall CreateAndQueuePreAuthEvent(__int64 a1, int a2, unsigned int a3, __int64 a4)
{
  unsigned int v8; // eax
  DWORD v9; // edi
  __int64 v10; // rbx
  DWORD LastError; // eax
  PVOID *v12; // rcx
  unsigned int v13; // r9d
  __int64 *v14; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19[9]; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_59a3304cf9193b99dca0f4d6fe619e9d_Traceguids);
  if ( a3 )
    v8 = 16 * (a3 + 2);
  else
    v8 = 48;
  v9 = 0;
  v10 = AllocWLMem(v8);
  if ( v10 )
    goto LABEL_8;
  LastError = GetLastError();
  v9 = LastError;
  if ( !LastError )
    goto LABEL_8;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_13d7b2876eef3b3479d595a943243812_Traceguids, LastError);
LABEL_8:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  v19[0] = v10;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
  {
    WPP_SF_q(v12[2], 11, WPP_13d7b2876eef3b3479d595a943243812_Traceguids, v10);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 1) != 0 )
      WPP_SF_d(v12[7], 11, WPP_59a3304cf9193b99dca0f4d6fe619e9d_Traceguids, v9);
    FreeMSMSecMemory(v19);
  }
  else
  {
    *(_QWORD *)(v10 + 16) = a1;
    v13 = 0;
    *(_DWORD *)(v10 + 24) = a2;
    *(_DWORD *)(v10 + 28) = a3;
    *(_QWORD *)(v10 + 8) = v10;
    *(_QWORD *)v10 = v10;
    if ( a3 )
    {
      v16 = 0;
      do
      {
        v17 = 2 * v16;
        v18 = 2 * (v16 + 2);
        ++v13;
        ++v16;
        *(_DWORD *)(v10 + 8 * v18) = *(_DWORD *)(a4 + 8 * v17);
        *(_DWORD *)(v10 + 8 * v17 + 36) = *(_DWORD *)(a4 + 8 * v17 + 4);
        *(_QWORD *)(v10 + 8 * v17 + 40) = *(_QWORD *)(a4 + 8 * v17 + 8);
      }
      while ( v13 < a3 );
    }
    v14 = *(__int64 **)(a1 + 56);
    if ( *v14 != a1 + 48 )
      __fastfail(3u);
    *(_QWORD *)v10 = a1 + 48;
    *(_QWORD *)(v10 + 8) = v14;
    *v14 = v10;
    *(_QWORD *)(a1 + 56) = v10;
    v9 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_59a3304cf9193b99dca0f4d6fe619e9d_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000aaec  push    rbx
0x18000aaee  push    rbp
0x18000aaef  push    rsi
0x18000aaf0  push    rdi
0x18000aaf1  push    r12
0x18000aaf3  push    r14
0x18000aaf5  push    r15
0x18000aaf7  sub     rsp, 30h
0x18000aafb  mov     r15, r9
0x18000aafe  mov     esi, r8d
0x18000ab01  mov     r14d, edx
0x18000ab04  mov     rbp, rcx
0x18000ab07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab0e  lea     r12, WPP_GLOBAL_Control
0x18000ab15  cmp     rcx, r12
0x18000ab18  jz      short loc_18000AB27
0x18000ab1a  test    dword ptr [rcx+44h], 100h
0x18000ab21  jnz     loc_18000AC12
0x18000ab27  test    esi, esi
0x18000ab29  jnz     loc_18000ABE7
0x18000ab2f  lea     eax, [rsi+30h]
0x18000ab32  mov     ecx, eax; dwBytes
0x18000ab34  xor     edi, edi
0x18000ab36  call    AllocWLMem
0x18000ab3b  mov     rbx, rax
0x18000ab3e  test    rax, rax
0x18000ab41  jnz     short loc_18000AB59
0x18000ab43  call    cs:__imp_GetLastError
0x18000ab4a  nop     dword ptr [rax+rax+00h]
0x18000ab4f  mov     edi, eax
0x18000ab51  test    eax, eax
0x18000ab53  jnz     loc_18000AC2C
0x18000ab59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab60  mov     [rsp+68h+var_48], rbx
0x18000ab65  cmp     rcx, r12
0x18000ab68  jz      short loc_18000AB74
0x18000ab6a  test    byte ptr [rcx+1Ch], 10h
0x18000ab6e  jnz     loc_18000AC63
0x18000ab74  test    edi, edi
0x18000ab76  jnz     short loc_18000ABAD
0x18000ab78  mov     [rbx+10h], rbp
0x18000ab7c  xor     r9d, r9d
0x18000ab7f  mov     [rbx+18h], r14d
0x18000ab83  mov     [rbx+1Ch], esi
0x18000ab86  mov     [rbx+8], rbx
0x18000ab8a  mov     [rbx], rbx
0x18000ab8d  test    esi, esi
0x18000ab8f  jnz     loc_18000AC87
0x18000ab95  lea     rax, [rbp+30h]
0x18000ab99  mov     rcx, [rax+8]
0x18000ab9d  cmp     [rcx], rax
0x18000aba0  jz      loc_18000ACC1
0x18000aba6  mov     ecx, 3
0x18000abab  int     29h; Win8: RtlFailFast(ecx)
0x18000abad  cmp     rcx, r12
0x18000abb0  jnz     short loc_18000ABF2
0x18000abb2  lea     rcx, [rsp+68h+var_48]
0x18000abb7  call    FreeMSMSecMemory
0x18000abbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abc3  cmp     rcx, r12
0x18000abc6  jz      short loc_18000ABD5
0x18000abc8  test    dword ptr [rcx+44h], 100h
0x18000abcf  jnz     loc_18000ACD6
0x18000abd5  mov     eax, edi
0x18000abd7  add     rsp, 30h
0x18000abdb  pop     r15
0x18000abdd  pop     r14
0x18000abdf  pop     r12
0x18000abe1  pop     rdi
0x18000abe2  pop     rsi
0x18000abe3  pop     rbp
0x18000abe4  pop     rbx
0x18000abe5  retn
0x18000abe7  lea     eax, [rsi+2]
0x18000abea  shl     eax, 4
0x18000abed  jmp     loc_18000AB32
0x18000abf2  test    byte ptr [rcx+44h], 1
0x18000abf6  jz      short loc_18000ABB2
0x18000abf8  mov     rcx, [rcx+38h]
0x18000abfc  lea     r8, WPP_59a3304cf9193b99dca0f4d6fe619e9d_Traceguids
0x18000ac03  mov     edx, 0Bh
0x18000ac08  mov     r9d, edi
0x18000ac0b  call    WPP_SF_d
0x18000ac10  jmp     short loc_18000ABB2
0x18000ac12  mov     rcx, [rcx+38h]
0x18000ac16  lea     r8, WPP_59a3304cf9193b99dca0f4d6fe619e9d_Traceguids
0x18000ac1d  mov     edx, 0Ah
0x18000ac22  call    WPP_SF_
0x18000ac27  jmp     loc_18000AB27
0x18000ac2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac33  cmp     rcx, r12
0x18000ac36  jz      loc_18000AB60
0x18000ac3c  test    byte ptr [rcx+1Ch], 1
0x18000ac40  jz      loc_18000AB60
0x18000ac46  mov     rcx, [rcx+10h]
0x18000ac4a  lea     r8, WPP_13d7b2876eef3b3479d595a943243812_Traceguids
0x18000ac51  mov     edx, 0Ah
0x18000ac56  mov     r9d, eax
0x18000ac59  call    WPP_SF_d
0x18000ac5e  jmp     loc_18000AB59
0x18000ac63  mov     rcx, [rcx+10h]
0x18000ac67  lea     r8, WPP_13d7b2876eef3b3479d595a943243812_Traceguids
0x18000ac6e  mov     edx, 0Bh
0x18000ac73  mov     r9, rbx
0x18000ac76  call    WPP_SF_q
0x18000ac7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac82  jmp     loc_18000AB74
0x18000ac87  xor     r8d, r8d
0x18000ac8a  mov     rdx, r8
0x18000ac8d  lea     rcx, [r8+2]
0x18000ac91  add     rdx, rdx
0x18000ac94  add     rcx, rcx
0x18000ac97  inc     r9d
0x18000ac9a  inc     r8
0x18000ac9d  mov     eax, [r15+rdx*8]
0x18000aca1  mov     [rbx+rcx*8], eax
0x18000aca4  mov     eax, [r15+rdx*8+4]
0x18000aca9  mov     [rbx+rdx*8+24h], eax
0x18000acad  mov     rax, [r15+rdx*8+8]
0x18000acb2  mov     [rbx+rdx*8+28h], rax
0x18000acb7  cmp     r9d, esi
0x18000acba  jb      short loc_18000AC8A
0x18000acbc  jmp     loc_18000AB95
0x18000acc1  mov     [rbx], rax
0x18000acc4  mov     [rbx+8], rcx
0x18000acc8  mov     [rcx], rbx
0x18000accb  mov     [rax+8], rbx
0x18000accf  xor     edi, edi
0x18000acd1  jmp     loc_18000ABBC
0x18000acd6  mov     rcx, [rcx+38h]
0x18000acda  lea     r8, WPP_59a3304cf9193b99dca0f4d6fe619e9d_Traceguids
0x18000ace1  mov     edx, 0Ch
0x18000ace6  mov     r9d, edi
0x18000ace9  call    WPP_SF_d
0x18000acee  jmp     loc_18000ABD5
```
