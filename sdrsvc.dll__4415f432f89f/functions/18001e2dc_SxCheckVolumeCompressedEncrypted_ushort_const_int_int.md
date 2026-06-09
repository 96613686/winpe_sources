# SxCheckVolumeCompressedEncrypted(ushort const *,int *,int *)

- ea: `0x18001e2dc`
- end: `0x18001e416`
- name: `?SxCheckVolumeCompressedEncrypted@@YAJPEBGPEAH1@Z`
- size: `314`
- prototype: `__int64 __fastcall(unsigned __int16 *, DWORD *, DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800148dc`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001e2dc`
- `0x18001f624`
- `0x18001fcf4`
- `0x180020488`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001e3b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001e3b5`

## string_xrefs

- `0x18001e2f1`: `SxCheckVolumeCompressedEncrypted`

## pseudocode

```c
__int64 __fastcall SxCheckVolumeCompressedEncrypted(unsigned __int16 *a1, DWORD *a2, DWORD *a3)
{
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  unsigned __int16 v8; // dx
  DWORD FileAttributesW; // eax
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-58h] BYREF
  int v12; // [rsp+30h] [rbp-48h] BYREF
  __int16 v13; // [rsp+34h] [rbp-44h]
  __int16 v14; // [rsp+36h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxCheckVolumeCompressedEncrypted", 167, 1);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_180028260;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v6 = 173;
  if ( a1 && (v13 = 173, v6 = 174, a2) && (v13 = 174, v6 = 175, a3) )
  {
    v12 = 0;
    v13 = 175;
    LastFailureAsHRESULT = CBsString::Append((CBsString *)lpFileName, a1);
    v12 = LastFailureAsHRESULT;
    v6 = 177;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v13 = 177;
      LastFailureAsHRESULT = CBsString::Trailing((CBsString *)lpFileName, v8);
      v12 = LastFailureAsHRESULT;
      v6 = 178;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v13 = 178;
        FileAttributesW = GetFileAttributesW(lpFileName[0]);
        if ( FileAttributesW != -1 )
        {
          v12 = 0;
          v13 = 181;
          *a2 = FileAttributesW & 0x800;
          LastFailureAsHRESULT = 0;
          *a3 = FileAttributesW & 0x4000;
          goto LABEL_15;
        }
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(0xFFFFFFFFLL);
        v12 = LastFailureAsHRESULT;
        v6 = 181;
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v12 = -2147024809;
  }
  v14 = v6;
LABEL_15:
  CBsString::_Release((LPVOID *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001e2dc  push    rbp
0x18001e2de  push    rbx
0x18001e2df  push    rsi
0x18001e2e0  push    rdi
0x18001e2e1  mov     rbp, rsp
0x18001e2e4  sub     rsp, 78h
0x18001e2e8  mov     rdi, r8
0x18001e2eb  mov     rsi, rdx
0x18001e2ee  mov     rbx, rcx
0x18001e2f1  lea     rdx, aSxcheckvolumec; "SxCheckVolumeCompressedEncrypted"
0x18001e2f8  mov     r8d, 0A7h; unsigned __int16
0x18001e2fe  lea     rcx, [rbp+var_48]; this
0x18001e302  mov     r9d, 1; unsigned __int16
0x18001e308  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e30d  mov     [rbp+var_50], 0
0x18001e315  lea     rax, qword_180028260
0x18001e31c  mov     [rbp+lpFileName], rax
0x18001e320  test    rsi, rsi
0x18001e323  jz      short loc_18001E32B
0x18001e325  mov     dword ptr [rsi], 0
0x18001e32b  test    rdi, rdi
0x18001e32e  jz      short loc_18001E336
0x18001e330  mov     dword ptr [rdi], 0
0x18001e336  mov     eax, 0ADh
0x18001e33b  test    rbx, rbx
0x18001e33e  jnz     short loc_18001E351
0x18001e340  mov     ebx, 80070057h
0x18001e345  mov     [rbp+var_48], ebx
0x18001e348  mov     [rbp+var_42], ax
0x18001e34c  jmp     loc_18001E3F9
0x18001e351  mov     [rbp+var_44], ax
0x18001e355  mov     eax, 0AEh
0x18001e35a  test    rsi, rsi
0x18001e35d  jz      short loc_18001E340
0x18001e35f  mov     [rbp+var_44], ax
0x18001e363  mov     eax, 0AFh
0x18001e368  test    rdi, rdi
0x18001e36b  jz      short loc_18001E340
0x18001e36d  mov     [rbp+var_48], 0
0x18001e374  mov     [rbp+var_44], ax
0x18001e378  mov     rdx, rbx; unsigned __int16 *
0x18001e37b  lea     rcx, [rbp+lpFileName]; this
0x18001e37f  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18001e384  mov     ebx, eax
0x18001e386  mov     [rbp+var_48], eax
0x18001e389  test    eax, eax
0x18001e38b  mov     eax, 0B1h
0x18001e390  js      short loc_18001E348
0x18001e392  lea     rcx, [rbp+lpFileName]; this
0x18001e396  mov     [rbp+var_44], ax
0x18001e39a  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18001e39f  mov     ebx, eax
0x18001e3a1  mov     [rbp+var_48], eax
0x18001e3a4  test    eax, eax
0x18001e3a6  mov     eax, 0B2h
0x18001e3ab  js      short loc_18001E348
0x18001e3ad  mov     rcx, [rbp+lpFileName]; lpFileName
0x18001e3b1  mov     [rbp+var_44], ax
0x18001e3b5  call    cs:__imp_GetFileAttributesW
0x18001e3bb  mov     ecx, eax
0x18001e3bd  cmp     eax, 0FFFFFFFFh
0x18001e3c0  jnz     short loc_18001E3D6
0x18001e3c2  call    GetLastFailureAsHRESULT
0x18001e3c7  mov     ebx, eax
0x18001e3c9  mov     [rbp+var_48], eax
0x18001e3cc  mov     eax, 0B5h
0x18001e3d1  jmp     loc_18001E348
0x18001e3d6  mov     eax, 0B5h
0x18001e3db  mov     [rbp+var_48], 0
0x18001e3e2  mov     [rbp+var_44], ax
0x18001e3e6  mov     eax, ecx
0x18001e3e8  and     eax, 800h
0x18001e3ed  and     ecx, 4000h
0x18001e3f3  mov     [rsi], eax
0x18001e3f5  xor     ebx, ebx
0x18001e3f7  mov     [rdi], ecx
0x18001e3f9  lea     rcx, [rbp+lpFileName]; this
0x18001e3fd  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001e402  lea     rcx, [rbp+var_48]; this
0x18001e406  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e40b  mov     eax, ebx
0x18001e40d  add     rsp, 78h
0x18001e411  pop     rdi
0x18001e412  pop     rsi
0x18001e413  pop     rbx
0x18001e414  pop     rbp
0x18001e415  retn
```
