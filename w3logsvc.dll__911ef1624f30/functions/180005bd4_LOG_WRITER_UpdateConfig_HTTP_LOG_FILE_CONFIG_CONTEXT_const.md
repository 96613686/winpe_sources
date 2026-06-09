# LOG_WRITER::UpdateConfig(HTTP_LOG_FILE_CONFIG_CONTEXT const *)

- ea: `0x180005bd4`
- end: `0x180005cc5`
- name: `?UpdateConfig@LOG_WRITER@@QEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const struct HTTP_LOG_FILE_CONFIG_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180007cf0`
- `0x180008858`

## callees

- `0x180004b28`
- `0x180005b3c`
- `0x180005bd4`
- `0x180005ccc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cb4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bfe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005c04`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005c04`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::UpdateConfig(RTL_SRWLOCK *this, const struct HTTP_LOG_FILE_CONFIG_CONTEXT *a2)
{
  int updated; // edi
  RTL_SRWLOCK *v5; // rbp
  unsigned int v6; // ecx
  _BYTE *Ptr; // rax

  if ( a2 )
  {
    v5 = this + 90;
    updated = 0;
    AcquireSRWLockExclusive(this + 90);
    this[83].Ptr = (PVOID)GetTickCount64();
    v6 = *((_DWORD *)a2 + 57);
    if ( (v6 & 0x7FFF) != 0 )
    {
      if ( ((v6 | ((v6 | ((v6 | (v6 >> 3)) >> 1)) >> 1)) & 2) != 0 || (v6 & 0x200) != 0 )
      {
        updated = LOG_WRITER::Flush((LOG_WRITER *)this, 1);
        if ( updated < 0 && !HIDWORD(this[84].Ptr) )
          goto LABEL_18;
        LOG_WRITER::ResetWriter((LOG_WRITER *)this);
        LODWORD(this[78].Ptr) = 0;
      }
      else if ( (v6 & 0x410) != 0
             || (v6 & 0x4000) != 0 && (*((_BYTE *)a2 + 40) & 1) != 0 && ((Ptr = this[1].Ptr) == 0 || (Ptr[40] & 1) == 0) )
      {
        updated = LOG_WRITER::Flush((LOG_WRITER *)this, 1);
        if ( updated < 0 && !HIDWORD(this[84].Ptr) )
          goto LABEL_18;
      }
      updated = LOG_WRITER::UpdateConfigHelper((LOG_WRITER *)this, a2);
    }
LABEL_18:
    ReleaseSRWLockExclusive(v5);
    return (unsigned int)updated;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180005bd4  push    rbx
0x180005bd6  push    rbp
0x180005bd7  push    rsi
0x180005bd8  push    rdi
0x180005bd9  sub     rsp, 28h
0x180005bdd  mov     rsi, rdx
0x180005be0  mov     rbx, rcx
0x180005be3  test    rdx, rdx
0x180005be6  jnz     short loc_180005BF2
0x180005be8  mov     edi, 80070057h
0x180005bed  jmp     loc_180005CBA
0x180005bf2  lea     rbp, [rcx+2D0h]
0x180005bf9  xor     edi, edi
0x180005bfb  mov     rcx, rbp; SRWLock
0x180005bfe  call    cs:__imp_AcquireSRWLockExclusive
0x180005c04  call    cs:__imp_GetTickCount64
0x180005c0a  mov     [rbx+298h], rax
0x180005c11  mov     ecx, [rsi+0E4h]
0x180005c17  test    ecx, 7FFFh
0x180005c1d  jz      loc_180005CB1
0x180005c23  mov     eax, ecx
0x180005c25  lea     edx, [rdi+1]; int
0x180005c28  shr     eax, 3
0x180005c2b  or      eax, ecx
0x180005c2d  shr     eax, 1
0x180005c2f  or      eax, ecx
0x180005c31  shr     eax, 1
0x180005c33  or      eax, ecx
0x180005c35  shr     eax, 1
0x180005c37  test    dl, al
0x180005c39  jnz     short loc_180005C7B
0x180005c3b  bt      ecx, 9
0x180005c3f  jb      short loc_180005C7B
0x180005c41  test    ecx, 410h
0x180005c47  jnz     short loc_180005C62
0x180005c49  bt      ecx, 0Eh
0x180005c4d  jnb     short loc_180005CA4
0x180005c4f  test    [rsi+28h], dl
0x180005c52  jz      short loc_180005CA4
0x180005c54  mov     rax, [rbx+8]
0x180005c58  test    rax, rax
0x180005c5b  jz      short loc_180005C62
0x180005c5d  test    [rax+28h], dl
0x180005c60  jnz     short loc_180005CA4
0x180005c62  mov     rcx, rbx; this
0x180005c65  call    ?Flush@LOG_WRITER@@AEAAJH@Z; LOG_WRITER::Flush(int)
0x180005c6a  mov     edi, eax
0x180005c6c  test    eax, eax
0x180005c6e  jns     short loc_180005CA4
0x180005c70  cmp     dword ptr [rbx+2A4h], 0
0x180005c77  jz      short loc_180005CB1
0x180005c79  jmp     short loc_180005CA4
0x180005c7b  mov     rcx, rbx; this
0x180005c7e  call    ?Flush@LOG_WRITER@@AEAAJH@Z; LOG_WRITER::Flush(int)
0x180005c83  mov     edi, eax
0x180005c85  test    eax, eax
0x180005c87  jns     short loc_180005C92
0x180005c89  cmp     dword ptr [rbx+2A4h], 0
0x180005c90  jz      short loc_180005CB1
0x180005c92  mov     rcx, rbx; this
0x180005c95  call    ?ResetWriter@LOG_WRITER@@AEAAXXZ; LOG_WRITER::ResetWriter(void)
0x180005c9a  mov     dword ptr [rbx+270h], 0
0x180005ca4  mov     rdx, rsi; struct HTTP_LOG_FILE_CONFIG_CONTEXT *
0x180005ca7  mov     rcx, rbx; this
0x180005caa  call    ?UpdateConfigHelper@LOG_WRITER@@AEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z; LOG_WRITER::UpdateConfigHelper(HTTP_LOG_FILE_CONFIG_CONTEXT const *)
0x180005caf  mov     edi, eax
0x180005cb1  mov     rcx, rbp; SRWLock
0x180005cb4  call    cs:__imp_ReleaseSRWLockExclusive
0x180005cba  mov     eax, edi
0x180005cbc  add     rsp, 28h
0x180005cc0  pop     rdi
0x180005cc1  pop     rsi
0x180005cc2  pop     rbp
0x180005cc3  pop     rbx
0x180005cc4  retn
```
