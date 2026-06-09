# CpuCallback

- ea: `0x1400032c0`
- end: `0x1400033b8`
- name: `CpuCallback`
- size: `248`
- prototype: `__int64 __fastcall(PEVENT_RECORD Event)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003a30`

## callees

- `0x1400032c0`
- `0x140004c2c`
- `0x140009c04`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003361`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003361`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003372`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003372`

## string_xrefs

- `0x140003301`: `MemSize`
- `0x140003328`: `ComputerName`

## pseudocode

```c
int __fastcall CpuCallback(PEVENT_RECORD Event)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int v6; // [rsp+20h] [rbp-228h] BYREF
  int v7[3]; // [rsp+24h] [rbp-224h] BYREF
  unsigned __int16 v8[256]; // [rsp+30h] [rbp-218h] BYREF

  v6 = 4;
  v7[0] = 0;
  v8[0] = 0;
  LODWORD(v2) = GetMofData(Event, L"MemSize", v7, &v6);
  if ( !(_DWORD)v2 )
  {
    dword_140082114 = v7[0];
    v6 = 512;
    LODWORD(v2) = GetMofData(Event, L"ComputerName", v8, &v6);
    if ( !(_DWORD)v2 )
    {
      v2 = -1;
      do
        ++v2;
      while ( v8[v2] );
      if ( (_DWORD)v2 )
      {
        v3 = (unsigned int)(v2 + 1);
        ProcessHeap = GetProcessHeap();
        v2 = (__int64)HeapAlloc(ProcessHeap, 8u, 2 * v3);
        lpMem = (unsigned __int16 *)v2;
        if ( v2 )
          LODWORD(v2) = StringCchCopyW((unsigned __int16 *)v2, (unsigned int)v3, v8);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400032c0  mov     [rsp+arg_8], rbx
0x1400032c5  mov     [rsp+arg_10], rsi
0x1400032ca  push    rdi
0x1400032cb  sub     rsp, 240h
0x1400032d2  mov     rax, cs:__security_cookie
0x1400032d9  xor     rax, rsp
0x1400032dc  mov     [rsp+248h+var_18], rax
0x1400032e4  xor     esi, esi
0x1400032e6  mov     [rsp+248h+var_228], 4
0x1400032ee  lea     r9, [rsp+248h+var_228]; unsigned int *
0x1400032f3  mov     [rsp+248h+var_224], esi
0x1400032f7  lea     r8, [rsp+248h+var_224]; void *
0x1400032fc  mov     [rsp+248h+var_218], si
0x140003301  lea     rdx, aMemsize; "MemSize"
0x140003308  mov     rbx, rcx
0x14000330b  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140003310  test    eax, eax
0x140003312  jnz     short loc_140003393
0x140003314  mov     eax, [rsp+248h+var_224]
0x140003318  lea     r9, [rsp+248h+var_228]; unsigned int *
0x14000331d  lea     r8, [rsp+248h+var_218]; void *
0x140003322  mov     cs:dword_140082114, eax
0x140003328  lea     rdx, aComputername; "ComputerName"
0x14000332f  mov     [rsp+248h+var_228], 200h
0x140003337  mov     rcx, rbx; Event
0x14000333a  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000333f  test    eax, eax
0x140003341  jnz     short loc_140003393
0x140003343  lea     rcx, [rsp+248h+var_218]
0x140003348  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000334c  inc     rax
0x14000334f  cmp     [rcx+rax*2], si
0x140003353  jnz     short loc_14000334C
0x140003355  test    eax, eax
0x140003357  jz      short loc_140003393
0x140003359  inc     eax
0x14000335b  mov     edi, eax
0x14000335d  lea     rbx, [rax+rax]
0x140003361  call    cs:__imp_GetProcessHeap
0x140003367  mov     r8, rbx; dwBytes
0x14000336a  mov     edx, 8; dwFlags
0x14000336f  mov     rcx, rax; hHeap
0x140003372  call    cs:__imp_HeapAlloc
0x140003378  mov     cs:lpMem, rax
0x14000337f  test    rax, rax
0x140003382  jz      short loc_140003393
0x140003384  lea     r8, [rsp+248h+var_218]; unsigned __int16 *
0x140003389  mov     edx, edi; unsigned __int64
0x14000338b  mov     rcx, rax; unsigned __int16 *
0x14000338e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140003393  mov     rcx, [rsp+248h+var_18]
0x14000339b  xor     rcx, rsp; StackCookie
0x14000339e  call    __security_check_cookie
0x1400033a3  lea     r11, [rsp+248h+var_8]
0x1400033ab  mov     rbx, [r11+18h]
0x1400033af  mov     rsi, [r11+20h]
0x1400033b3  mov     rsp, r11
0x1400033b6  pop     rdi
0x1400033b7  retn
```
