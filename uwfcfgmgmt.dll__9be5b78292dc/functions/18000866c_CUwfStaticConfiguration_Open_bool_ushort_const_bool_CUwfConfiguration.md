# CUwfStaticConfiguration::Open(bool,ushort const *,bool,CUwfConfiguration *)

- ea: `0x18000866c`
- end: `0x18000872a`
- name: `?Open@CUwfStaticConfiguration@@AEAAJ_NPEBG0PEAVCUwfConfiguration@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(HKEY *this, char, const unsigned __int16 *, char, struct CUwfConfiguration *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008730`

## callees

- `0x180006240`
- `0x18000866c`
- `0x18000de30`
- `0x18000df60`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::Open(
        HKEY *this,
        char a2,
        const unsigned __int16 *a3,
        char a4,
        struct CUwfConfiguration *a5)
{
  bool v9; // cl
  bool v10; // cf
  void *v11; // rcx
  REGSAM v12; // ebx
  __int64 result; // rax
  HKEY v14; // rax
  HKEY *v15; // rcx
  HKEY v16; // rdx

  CUwfStaticConfiguration::Close(this);
  *((_BYTE *)this + 8) = a4;
  v9 = a4 || !a2;
  *((_BYTE *)this + 9) = v9;
  v10 = v9;
  this[4] = (HKEY)a5;
  v11 = (void *)*((_QWORD *)a5 + 1);
  v12 = v10 ? 131097 : 131103;
  if ( v11 == (void *)-1LL )
    result = CUwfRegKey::Open(this + 2, HKEY_LOCAL_MACHINE, a3, v12);
  else
    result = CUwfRegKey::OpenTransacted(this + 2, HKEY_LOCAL_MACHINE, a3, v12, v11);
  if ( (int)result >= 0 )
  {
    v14 = this[4];
    v15 = this + 3;
    v16 = this[2];
    if ( *((_QWORD *)v14 + 1) == -1 )
      return CUwfRegKey::Open(v15, v16, L"Volumes", v12);
    else
      return CUwfRegKey::OpenTransacted(v15, v16, L"Volumes", v12, *((HANDLE *)v14 + 1));
  }
  return result;
}

```

## disassembly

```asm
0x18000866c  push    rbx
0x18000866e  push    rbp
0x18000866f  push    rsi
0x180008670  push    rdi
0x180008671  sub     rsp, 38h
0x180008675  mov     bl, r9b
0x180008678  mov     rbp, r8
0x18000867b  mov     sil, dl
0x18000867e  mov     rdi, rcx
0x180008681  call    ?Close@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::Close(void)
0x180008686  mov     [rdi+8], bl
0x180008689  test    bl, bl
0x18000868b  jnz     short loc_180008696
0x18000868d  test    sil, sil
0x180008690  jz      short loc_180008696
0x180008692  xor     cl, cl
0x180008694  jmp     short loc_180008698
0x180008696  mov     cl, 1
0x180008698  mov     rax, [rsp+58h+arg_20]
0x1800086a0  lea     rsi, [rdi+10h]
0x1800086a4  mov     [rdi+9], cl
0x1800086a7  mov     r8, rbp; lpSubKey
0x1800086aa  neg     cl
0x1800086ac  mov     [rdi+20h], rax
0x1800086b0  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800086b7  mov     rcx, [rax+8]
0x1800086bb  sbb     ebx, ebx
0x1800086bd  and     ebx, 0FFFFFFFAh
0x1800086c0  add     ebx, 2001Fh
0x1800086c6  mov     r9d, ebx; samDesired
0x1800086c9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800086cd  jz      short loc_1800086DE
0x1800086cf  mov     [rsp+58h+var_38], rcx; HANDLE
0x1800086d4  mov     rcx, rsi; phkResult
0x1800086d7  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x1800086dc  jmp     short loc_1800086E6
0x1800086de  mov     rcx, rsi; phkResult
0x1800086e1  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800086e6  test    eax, eax
0x1800086e8  js      short loc_180008721
0x1800086ea  mov     rax, [rdi+20h]
0x1800086ee  lea     rcx, [rdi+18h]; phkResult
0x1800086f2  mov     rdx, [rsi]; hKey
0x1800086f5  mov     r9d, ebx; samDesired
0x1800086f8  mov     r8, [rax+8]
0x1800086fc  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180008700  jz      short loc_180008715
0x180008702  mov     [rsp+58h+var_38], r8; HANDLE
0x180008707  lea     r8, aVolumes; "Volumes"
0x18000870e  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x180008713  jmp     short loc_180008721
0x180008715  lea     r8, aVolumes; "Volumes"
0x18000871c  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008721  add     rsp, 38h
0x180008725  pop     rdi
0x180008726  pop     rsi
0x180008727  pop     rbp
0x180008728  pop     rbx
0x180008729  retn
```
