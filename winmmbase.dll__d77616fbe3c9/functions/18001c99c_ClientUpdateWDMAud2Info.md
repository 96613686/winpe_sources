# ClientUpdateWDMAud2Info

- ea: `0x18001c99c`
- end: `0x18001caaf`
- name: `ClientUpdateWDMAud2Info`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f9e0`
- `0x18000fa30`

## callees

- `0x18001c99c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ca2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ca2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c9b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c9b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001caa8`

## pseudocode

```c
void ClientUpdateWDMAud2Info()
{
  __int64 v0; // rdi
  __int64 **v1; // rsi
  __int64 *i; // rbx
  int v3; // eax
  _QWORD v4[2]; // [rsp+30h] [rbp-28h]
  _QWORD v5[3]; // [rsp+40h] [rbp-18h]
  int v6; // [rsp+60h] [rbp+8h]
  int v7; // [rsp+64h] [rbp+Ch]

  EnterCriticalSection(&NumDevsCritSec);
  v6 = 53;
  v4[0] = &midiindrvZ;
  v0 = 0;
  v7 = 1;
  v4[1] = &midioutdrvZ;
  v5[0] = &wTotalMidiInDevs;
  v5[1] = &wTotalMidiOutDevs;
  do
  {
    v1 = (__int64 **)v4[v0];
    for ( i = *v1; i != (__int64 *)v1; i = (__int64 *)*i )
    {
      if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)i + 80, -1, L"wdmaud2.drv", -1) == 2 )
      {
        v3 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, _QWORD))i[10])(
               0,
               (unsigned int)*(&v6 + v0),
               0,
               i[13],
               0);
        if ( !HIWORD(v3) && *((_DWORD *)i + 22) != (unsigned __int16)v3 )
        {
          *(_DWORD *)v5[v0] += (unsigned __int16)v3 - *((_DWORD *)i + 22);
          *((_DWORD *)i + 22) = (unsigned __int16)v3;
        }
        break;
      }
    }
    ++v0;
  }
  while ( v0 != 2 );
  LeaveCriticalSection(&NumDevsCritSec);
}

```

## disassembly

```asm
0x18001c99c  mov     [rsp+arg_8], rbx
0x18001c9a1  mov     [rsp+arg_10], rsi
0x18001c9a6  push    rdi
0x18001c9a7  sub     rsp, 50h
0x18001c9ab  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18001c9b2  call    cs:__imp_EnterCriticalSection
0x18001c9b8  lea     rax, midiindrvZ
0x18001c9bf  mov     [rsp+58h+arg_0], 35h ; '5'
0x18001c9c7  mov     [rsp+58h+var_28], rax
0x18001c9cc  xor     edi, edi
0x18001c9ce  lea     rax, midioutdrvZ
0x18001c9d5  mov     [rsp+58h+arg_4], 1
0x18001c9dd  mov     [rsp+58h+var_20], rax
0x18001c9e2  lea     rax, wTotalMidiInDevs
0x18001c9e9  mov     [rsp+58h+var_18], rax
0x18001c9ee  lea     rax, wTotalMidiOutDevs
0x18001c9f5  mov     [rsp+58h+var_10], rax
0x18001c9fa  mov     rsi, [rsp+rdi*8+58h+var_28]
0x18001c9ff  mov     rbx, [rsi]
0x18001ca02  jmp     short loc_18001CA38
0x18001ca04  or      r9d, 0FFFFFFFFh; cchCount1
0x18001ca08  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001ca10  lea     rax, String2; "wdmaud2.drv"
0x18001ca17  lea     r8, [rbx+0A0h]; lpString1
0x18001ca1e  mov     [rsp+58h+lpString2], rax; lpString2
0x18001ca23  lea     edx, [r9+2]; dwCmpFlags
0x18001ca27  lea     ecx, [rdx+7Eh]; Locale
0x18001ca2a  call    cs:__imp_CompareStringW
0x18001ca30  cmp     eax, 2
0x18001ca33  jz      short loc_18001CA3F
0x18001ca35  mov     rbx, [rbx]
0x18001ca38  cmp     rbx, rsi
0x18001ca3b  jnz     short loc_18001CA04
0x18001ca3d  jmp     short loc_18001CA85
0x18001ca3f  mov     r9, [rbx+68h]
0x18001ca43  xor     r8d, r8d
0x18001ca46  mov     edx, [rsp+rdi*4+58h+arg_0]
0x18001ca4a  xor     ecx, ecx
0x18001ca4c  mov     rax, [rbx+50h]
0x18001ca50  mov     [rsp+58h+lpString2], 0
0x18001ca59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca5e  mov     edx, eax
0x18001ca60  xor     ecx, ecx
0x18001ca62  shr     edx, 10h
0x18001ca65  cmp     cx, dx
0x18001ca68  jnz     short loc_18001CA85
0x18001ca6a  movzx   r8d, ax
0x18001ca6e  cmp     [rbx+58h], r8d
0x18001ca72  jz      short loc_18001CA85
0x18001ca74  mov     rdx, [rsp+rdi*8+58h+var_18]
0x18001ca79  mov     eax, r8d
0x18001ca7c  sub     eax, [rbx+58h]
0x18001ca7f  add     [rdx], eax
0x18001ca81  mov     [rbx+58h], r8d
0x18001ca85  inc     rdi
0x18001ca88  cmp     rdi, 2
0x18001ca8c  jnz     loc_18001C9FA
0x18001ca92  lea     rcx, NumDevsCritSec
0x18001ca99  mov     rbx, [rsp+58h+arg_8]
0x18001ca9e  mov     rsi, [rsp+58h+arg_10]
0x18001caa3  add     rsp, 50h
0x18001caa7  pop     rdi
0x18001caa8  jmp     cs:__imp_LeaveCriticalSection
```
