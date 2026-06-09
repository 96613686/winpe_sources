# CBannedDeviceIds::Remove(_WDS_DEVICE_ID const *)

- ea: `0x180025620`
- end: `0x1800257b4`
- name: `?Remove@CBannedDeviceIds@@QEAAKPEBU_WDS_DEVICE_ID@@@Z`
- size: `404`
- prototype: `unsigned int(CBannedDeviceIds *__hidden this, const struct _WDS_DEVICE_ID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180025550`

## callees

- `0x180017bd0`
- `0x180025250`
- `0x180025620`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180025767`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025767`
- `KERNEL32!EnterCriticalSection` at `0x1800256ce`
- `KERNEL32!EnterCriticalSection` at `0x1800256ce`
- `KERNEL32!LeaveCriticalSection` at `0x1800256e1`
- `KERNEL32!LeaveCriticalSection` at `0x1800256e1`

## string_xrefs

- `0x18002564a`: `-> CBannedDeviceIds::Remove`
- `0x180025786`: `<- CBannedDeviceIds::Remove=%x`
- `0x18002569d`: `CBannedDeviceIds::Remove: DeviceId={%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}`

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
0x180025620  mov     [rsp+arg_8], rbx
0x180025625  mov     [rsp+arg_10], rbp
0x18002562a  mov     [rsp+arg_18], rsi
0x18002562f  push    rdi
0x180025630  push    r14
0x180025632  push    r15
0x180025634  sub     rsp, 70h
0x180025638  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002563f  mov     r15, rdx
0x180025642  mov     r14, rcx
0x180025645  test    rax, rax
0x180025648  jz      short loc_18002565B
0x18002564a  lea     rdx, aCbanneddevicei_8; "-> CBannedDeviceIds::Remove"
0x180025651  mov     ecx, 10000h
0x180025656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002565b  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025662  test    rax, rax
0x180025665  jz      short loc_1800256CA
0x180025667  movzx   ecx, byte ptr [r15+0Fh]
0x18002566c  movzx   edx, byte ptr [r15+0Eh]
0x180025671  movzx   r10d, byte ptr [r15+0Dh]
0x180025676  movzx   r11d, byte ptr [r15+0Ch]
0x18002567b  movzx   ebx, byte ptr [r15+0Bh]
0x180025680  movzx   edi, byte ptr [r15+0Ah]
0x180025685  movzx   esi, byte ptr [r15+9]
0x18002568a  movzx   ebp, byte ptr [r15+8]
0x18002568f  movzx   r9d, word ptr [r15+6]
0x180025694  movzx   r8d, word ptr [r15+4]
0x180025699  mov     [rsp+88h+var_30], ecx
0x18002569d  lea     rcx, aCbanneddevicei_6; "CBannedDeviceIds::Remove: DeviceId={%08"...
0x1800256a4  mov     [rsp+88h+var_38], edx
0x1800256a8  mov     edx, [r15]
0x1800256ab  mov     [rsp+88h+var_40], r10d
0x1800256b0  mov     [rsp+88h+var_48], r11d
0x1800256b5  mov     [rsp+88h+var_50], ebx
0x1800256b9  mov     [rsp+88h+var_58], edi
0x1800256bd  mov     [rsp+88h+var_60], esi
0x1800256c1  mov     [rsp+88h+var_68], ebp
0x1800256c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256ca  lea     rcx, [r14+10h]; lpCriticalSection
0x1800256ce  call    cs:__imp_EnterCriticalSection
0x1800256d5  nop     dword ptr [rax+rax+00h]
0x1800256da  mov     rbx, [r14]
0x1800256dd  lea     rcx, [r14+10h]; lpCriticalSection
0x1800256e1  call    cs:__imp_LeaveCriticalSection
0x1800256e8  nop     dword ptr [rax+rax+00h]
0x1800256ed  test    rbx, rbx
0x1800256f0  jnz     short loc_1800256F6
0x1800256f2  xor     ecx, ecx
0x1800256f4  jmp     short loc_1800256F9
0x1800256f6  mov     rcx, [r14]
0x1800256f9  mov     [rsp+88h+arg_0], rcx
0x180025701  mov     ebx, 1
0x180025706  test    rcx, rcx
0x180025709  jz      short loc_180025775
0x18002570b  mov     rsi, rcx
0x18002570e  mov     rdx, rcx
0x180025711  mov     rax, rcx
0x180025714  neg     rax
0x180025717  sbb     rdi, rdi
0x18002571a  and     rdi, rsi
0x18002571d  test    rcx, rcx
0x180025720  mov     rcx, rdi; struct _WDS_DEVICE_ID *
0x180025723  cmovz   rsi, rdx
0x180025727  mov     rdx, r15; struct _WDS_DEVICE_ID *
0x18002572a  call    ?DeviceIdsEqual@@YAHPEBU_WDS_DEVICE_ID@@0@Z; DeviceIdsEqual(_WDS_DEVICE_ID const *,_WDS_DEVICE_ID const *)
0x18002572f  test    eax, eax
0x180025731  jnz     short loc_18002574F
0x180025733  mov     rcx, [rsi+88h]
0x18002573a  mov     [rsp+88h+arg_0], rcx
0x180025742  mov     rsi, rcx
0x180025745  mov     rdx, rcx
0x180025748  test    rcx, rcx
0x18002574b  jnz     short loc_180025711
0x18002574d  jmp     short loc_180025775
0x18002574f  lea     rdx, [rsp+88h+arg_0]
0x180025757  mov     rcx, r14
0x18002575a  call    ?DeleteAt@?$CList@UDeviceIdEntry@CBannedDeviceIds@@VCCriticalSection@@@@QEAAPEAUDeviceIdEntry@CBannedDeviceIds@@AEAPEAX@Z; CList<CBannedDeviceIds::DeviceIdEntry,CCriticalSection>::DeleteAt(void * &)
0x18002575f  test    rdi, rdi
0x180025762  jz      short loc_180025773
0x180025764  mov     rcx, rdi
0x180025767  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002576e  nop     dword ptr [rax+rax+00h]
0x180025773  xor     ebx, ebx
0x180025775  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002577c  add     ebx, ebx
0x18002577e  test    rax, rax
0x180025781  jz      short loc_180025797
0x180025783  mov     r8d, ebx
0x180025786  lea     rdx, aCbanneddevicei_12; "<- CBannedDeviceIds::Remove=%x"
0x18002578d  mov     ecx, 10000h
0x180025792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025797  lea     r11, [rsp+88h+var_18]
0x18002579c  mov     eax, ebx
0x18002579e  mov     rbx, [r11+28h]
0x1800257a2  mov     rbp, [r11+30h]
0x1800257a6  mov     rsi, [r11+38h]
0x1800257aa  mov     rsp, r11
0x1800257ad  pop     r15
0x1800257af  pop     r14
0x1800257b1  pop     rdi
0x1800257b2  retn
```
