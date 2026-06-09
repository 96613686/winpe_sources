# CBannedDeviceIds::Remove(_WDS_DEVICE_ID const *)

- ea: `0x180024550`
- end: `0x1800246dd`
- name: `?Remove@CBannedDeviceIds@@QEAAKPEBU_WDS_DEVICE_ID@@@Z`
- size: `397`
- prototype: `unsigned int(CBannedDeviceIds *__hidden this, const struct _WDS_DEVICE_ID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180024480`

## callees

- `0x180016e40`
- `0x180024180`
- `0x180024550`
- `0x18002e468`
- `0x180030010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800245fe`
- `KERNEL32!EnterCriticalSection` at `0x1800245fe`
- `KERNEL32!LeaveCriticalSection` at `0x180024611`
- `KERNEL32!LeaveCriticalSection` at `0x180024611`

## string_xrefs

- `0x18002457a`: `-> CBannedDeviceIds::Remove`
- `0x1800246af`: `<- CBannedDeviceIds::Remove=%x`
- `0x1800245cd`: `CBannedDeviceIds::Remove: DeviceId={%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}`

## pseudocode

```c
__int64 __fastcall CBannedDeviceIds::Remove(CBannedDeviceIds *this, const struct _WDS_DEVICE_ID *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // rsi
  const struct _WDS_DEVICE_ID *v8; // rdi
  unsigned int v9; // ebx
  __int64 v11; // [rsp+90h] [rbp+8h] BYREF

  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(0x10000u, L"-> CBannedDeviceIds::Remove");
  if ( g_ErrLibTraceFunction )
    g_ErrLibTraceFunction(
      L"CBannedDeviceIds::Remove: DeviceId={%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
      *(unsigned int *)a2,
      *((unsigned __int16 *)a2 + 2),
      *((unsigned __int16 *)a2 + 3),
      *((unsigned __int8 *)a2 + 8),
      *((unsigned __int8 *)a2 + 9),
      *((unsigned __int8 *)a2 + 10),
      *((unsigned __int8 *)a2 + 11),
      *((unsigned __int8 *)a2 + 12),
      *((unsigned __int8 *)a2 + 13),
      *((unsigned __int8 *)a2 + 14),
      *((unsigned __int8 *)a2 + 15));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = *(_QWORD *)this;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 )
    v5 = *(_QWORD *)this;
  else
    v5 = 0;
  v11 = v5;
  v6 = 1;
  if ( v5 )
  {
    v7 = v5;
    while ( 1 )
    {
      v8 = (const struct _WDS_DEVICE_ID *)(v7 & -(__int64)(v5 != 0));
      if ( (unsigned int)DeviceIdsEqual(v8, a2) )
        break;
      v5 = *(_QWORD *)(v7 + 136);
      v11 = v5;
      v7 = v5;
      if ( !v5 )
        goto LABEL_16;
    }
    CList<CBannedDeviceIds::DeviceIdEntry,CCriticalSection>::DeleteAt(this, &v11);
    if ( v8 )
      operator delete(v8);
    v6 = 0;
  }
LABEL_16:
  v9 = 2 * v6;
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(0x10000u, L"<- CBannedDeviceIds::Remove=%x", v9);
  return v9;
}

```

## disassembly

```asm
0x180024550  mov     [rsp+arg_8], rbx
0x180024555  mov     [rsp+arg_10], rbp
0x18002455a  mov     [rsp+arg_18], rsi
0x18002455f  push    rdi
0x180024560  push    r14
0x180024562  push    r15
0x180024564  sub     rsp, 70h
0x180024568  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002456f  mov     r15, rdx
0x180024572  mov     r14, rcx
0x180024575  test    rax, rax
0x180024578  jz      short loc_18002458B
0x18002457a  lea     rdx, aCbanneddevicei_8; "-> CBannedDeviceIds::Remove"
0x180024581  mov     ecx, 10000h
0x180024586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002458b  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180024592  test    rax, rax
0x180024595  jz      short loc_1800245FA
0x180024597  movzx   ecx, byte ptr [r15+0Fh]
0x18002459c  movzx   edx, byte ptr [r15+0Eh]
0x1800245a1  movzx   r10d, byte ptr [r15+0Dh]
0x1800245a6  movzx   r11d, byte ptr [r15+0Ch]
0x1800245ab  movzx   ebx, byte ptr [r15+0Bh]
0x1800245b0  movzx   edi, byte ptr [r15+0Ah]
0x1800245b5  movzx   esi, byte ptr [r15+9]
0x1800245ba  movzx   ebp, byte ptr [r15+8]
0x1800245bf  movzx   r9d, word ptr [r15+6]
0x1800245c4  movzx   r8d, word ptr [r15+4]
0x1800245c9  mov     [rsp+88h+var_30], ecx
0x1800245cd  lea     rcx, aCbanneddevicei_6; "CBannedDeviceIds::Remove: DeviceId={%08"...
0x1800245d4  mov     [rsp+88h+var_38], edx
0x1800245d8  mov     edx, [r15]
0x1800245db  mov     [rsp+88h+var_40], r10d
0x1800245e0  mov     [rsp+88h+var_48], r11d
0x1800245e5  mov     [rsp+88h+var_50], ebx
0x1800245e9  mov     [rsp+88h+var_58], edi
0x1800245ed  mov     [rsp+88h+var_60], esi
0x1800245f1  mov     [rsp+88h+var_68], ebp
0x1800245f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245fa  lea     rcx, [r14+10h]; lpCriticalSection
0x1800245fe  call    cs:__imp_EnterCriticalSection
0x180024605  nop     dword ptr [rax+rax+00h]
0x18002460a  mov     rbx, [r14]
0x18002460d  lea     rcx, [r14+10h]; lpCriticalSection
0x180024611  call    cs:__imp_LeaveCriticalSection
0x180024618  nop     dword ptr [rax+rax+00h]
0x18002461d  test    rbx, rbx
0x180024620  jnz     short loc_180024626
0x180024622  xor     ecx, ecx
0x180024624  jmp     short loc_180024629
0x180024626  mov     rcx, [r14]
0x180024629  mov     [rsp+88h+arg_0], rcx
0x180024631  mov     ebx, 1
0x180024636  test    rcx, rcx
0x180024639  jz      short loc_18002469E
0x18002463b  mov     rsi, rcx
0x18002463e  mov     rdx, rcx
0x180024641  mov     rax, rcx
0x180024644  neg     rax
0x180024647  sbb     rdi, rdi
0x18002464a  and     rdi, rsi
0x18002464d  test    rcx, rcx
0x180024650  mov     rcx, rdi; struct _WDS_DEVICE_ID *
0x180024653  cmovz   rsi, rdx
0x180024657  mov     rdx, r15; struct _WDS_DEVICE_ID *
0x18002465a  call    ?DeviceIdsEqual@@YAHPEBU_WDS_DEVICE_ID@@0@Z; DeviceIdsEqual(_WDS_DEVICE_ID const *,_WDS_DEVICE_ID const *)
0x18002465f  test    eax, eax
0x180024661  jnz     short loc_18002467F
0x180024663  mov     rcx, [rsi+88h]
0x18002466a  mov     [rsp+88h+arg_0], rcx
0x180024672  mov     rsi, rcx
0x180024675  mov     rdx, rcx
0x180024678  test    rcx, rcx
0x18002467b  jnz     short loc_180024641
0x18002467d  jmp     short loc_18002469E
0x18002467f  lea     rdx, [rsp+88h+arg_0]
0x180024687  mov     rcx, r14
0x18002468a  call    ?DeleteAt@?$CList@UDeviceIdEntry@CBannedDeviceIds@@VCCriticalSection@@@@QEAAPEAUDeviceIdEntry@CBannedDeviceIds@@AEAPEAX@Z; CList<CBannedDeviceIds::DeviceIdEntry,CCriticalSection>::DeleteAt(void * &)
0x18002468f  test    rdi, rdi
0x180024692  jz      short loc_18002469C
0x180024694  mov     rcx, rdi; lpMem
0x180024697  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002469c  xor     ebx, ebx
0x18002469e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800246a5  add     ebx, ebx
0x1800246a7  test    rax, rax
0x1800246aa  jz      short loc_1800246C0
0x1800246ac  mov     r8d, ebx
0x1800246af  lea     rdx, aCbanneddevicei_12; "<- CBannedDeviceIds::Remove=%x"
0x1800246b6  mov     ecx, 10000h
0x1800246bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246c0  lea     r11, [rsp+88h+var_18]
0x1800246c5  mov     eax, ebx
0x1800246c7  mov     rbx, [r11+28h]
0x1800246cb  mov     rbp, [r11+30h]
0x1800246cf  mov     rsi, [r11+38h]
0x1800246d3  mov     rsp, r11
0x1800246d6  pop     r15
0x1800246d8  pop     r14
0x1800246da  pop     rdi
0x1800246db  retn
```
