# mseClose(midiemu_tag *)

- ea: `0x18001e1fc`
- end: `0x18001e33e`
- name: `?mseClose@@YAIPEAUmidiemu_tag@@@Z`
- size: `322`
- prototype: `unsigned int __fastcall(struct midiemu_tag *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001fb58`

## callees

- `0x180012d08`
- `0x180019330`
- `0x18001e1d4`
- `0x18001e1fc`
- `0x18001ebc0`
- `0x18001ef64`
- `0x18001efbc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e2c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e32c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e2c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e32c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e313`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e313`

## pseudocode

```c
__int64 __fastcall mseClose(struct midiemu_tag *a1)
{
  unsigned int i; // edi
  MMRESULT v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  struct midiemu_tag *v6; // rax
  struct midiemu_tag *v7; // rdx
  struct midiemu_tag *v8; // rcx
  HANDLE v9; // rcx

  if ( (unsigned int)(*((_DWORD *)a1 + 19) - 2) > 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a5414217d91338b5429dfea51ae86c50_Traceguids);
    }
    mseOutStop(a1);
  }
  midiOutAllNotesOff(a1);
  for ( i = 0; i < *((_DWORD *)a1 + 49); ++i )
  {
    v3 = midiOutClose(*((HMIDIOUT *)a1 + 2 * i + 27));
    if ( v3
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, *((_QWORD *)a1 + 2 * i + 27), v3);
    }
  }
  HeapFree(hHeap, 0, *((LPVOID *)a1 + 23));
  v6 = gpEmuList;
  v7 = 0;
  if ( gpEmuList )
  {
    while ( 1 )
    {
      v8 = *(struct midiemu_tag **)v6;
      if ( v6 == a1 )
        break;
      v7 = v6;
      v6 = *(struct midiemu_tag **)v6;
      if ( !v8 )
        goto LABEL_22;
    }
    if ( v7 )
      *(_QWORD *)v7 = v8;
    else
      gpEmuList = *(struct midiemu_tag **)v6;
  }
LABEL_22:
  while ( *((int *)a1 + 5) >= 0 )
    PDEVUNLOCK(a1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 24));
  v9 = hHeap;
  *((_DWORD *)a1 + 16) = 0;
  HeapFree(v9, 0, a1);
  return 0;
}

```

## disassembly

```asm
0x18001e1fc  push    rbx
0x18001e1fe  push    rsi
0x18001e1ff  push    rdi
0x18001e200  push    r15
0x18001e202  sub     rsp, 38h
0x18001e206  mov     eax, [rcx+4Ch]
0x18001e209  lea     r15, WPP_GLOBAL_Control
0x18001e210  sub     eax, 2
0x18001e213  mov     rbx, rcx
0x18001e216  cmp     eax, 2
0x18001e219  jbe     short loc_18001E253
0x18001e21b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e222  cmp     rcx, r15
0x18001e225  jz      short loc_18001E24B
0x18001e227  test    dword ptr [rcx+1Ch], 400000h
0x18001e22e  jz      short loc_18001E24B
0x18001e230  cmp     byte ptr [rcx+19h], 1
0x18001e234  jb      short loc_18001E24B
0x18001e236  mov     rcx, [rcx+10h]
0x18001e23a  lea     r8, WPP_a5414217d91338b5429dfea51ae86c50_Traceguids
0x18001e241  mov     edx, 11h
0x18001e246  call    WPP_SF_
0x18001e24b  mov     rcx, rbx; struct midiemu_tag *
0x18001e24e  call    ?mseOutStop@@YAIPEAUmidiemu_tag@@@Z; mseOutStop(midiemu_tag *)
0x18001e253  mov     rcx, rbx
0x18001e256  call    midiOutAllNotesOff
0x18001e25b  xor     edi, edi
0x18001e25d  cmp     [rbx+0C4h], edi
0x18001e263  jbe     short loc_18001E2B5
0x18001e265  mov     esi, edi
0x18001e267  add     rsi, rsi
0x18001e26a  mov     rcx, [rbx+rsi*8+0D8h]; hmo
0x18001e272  call    midiOutClose
0x18001e277  test    eax, eax
0x18001e279  jz      short loc_18001E2AB
0x18001e27b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e282  cmp     rcx, r15
0x18001e285  jz      short loc_18001E2AB
0x18001e287  test    dword ptr [rcx+1Ch], 400000h
0x18001e28e  jz      short loc_18001E2AB
0x18001e290  cmp     byte ptr [rcx+19h], 1
0x18001e294  jb      short loc_18001E2AB
0x18001e296  mov     r9, [rbx+rsi*8+0D8h]
0x18001e29e  mov     rcx, [rcx+10h]
0x18001e2a2  mov     [rsp+58h+var_38], eax
0x18001e2a6  call    WPP_SF_qD
0x18001e2ab  inc     edi
0x18001e2ad  cmp     edi, [rbx+0C4h]
0x18001e2b3  jb      short loc_18001E265
0x18001e2b5  mov     r8, [rbx+0B8h]; lpMem
0x18001e2bc  xor     edx, edx; dwFlags
0x18001e2be  mov     rcx, cs:hHeap; hHeap
0x18001e2c5  call    cs:__imp_HeapFree
0x18001e2cb  mov     rax, cs:?gpEmuList@@3PEAUmidiemu_tag@@EA; midiemu_tag * gpEmuList
0x18001e2d2  xor     edx, edx
0x18001e2d4  test    rax, rax
0x18001e2d7  jz      short loc_18001E309
0x18001e2d9  mov     rcx, [rax]
0x18001e2dc  cmp     rax, rbx
0x18001e2df  jz      short loc_18001E2EE
0x18001e2e1  mov     rdx, rax
0x18001e2e4  mov     rax, rcx
0x18001e2e7  test    rcx, rcx
0x18001e2ea  jnz     short loc_18001E2D9
0x18001e2ec  jmp     short loc_18001E309
0x18001e2ee  test    rdx, rdx
0x18001e2f1  jz      short loc_18001E2F8
0x18001e2f3  mov     [rdx], rcx
0x18001e2f6  jmp     short loc_18001E309
0x18001e2f8  mov     cs:?gpEmuList@@3PEAUmidiemu_tag@@EA, rcx; midiemu_tag * gpEmuList
0x18001e2ff  jmp     short loc_18001E309
0x18001e301  mov     rcx, rbx; struct midiemu_tag *
0x18001e304  call    ?PDEVUNLOCK@@YAJPEAUmidiemu_tag@@@Z; PDEVUNLOCK(midiemu_tag *)
0x18001e309  cmp     dword ptr [rbx+14h], 0
0x18001e30d  jge     short loc_18001E301
0x18001e30f  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001e313  call    cs:__imp_DeleteCriticalSection
0x18001e319  mov     rcx, cs:hHeap; hHeap
0x18001e320  mov     r8, rbx; lpMem
0x18001e323  xor     edx, edx; dwFlags
0x18001e325  mov     dword ptr [rbx+40h], 0
0x18001e32c  call    cs:__imp_HeapFree
0x18001e332  xor     eax, eax
0x18001e334  add     rsp, 38h
0x18001e338  pop     r15
0x18001e33a  pop     rdi
0x18001e33b  pop     rsi
0x18001e33c  pop     rbx
0x18001e33d  retn
```
