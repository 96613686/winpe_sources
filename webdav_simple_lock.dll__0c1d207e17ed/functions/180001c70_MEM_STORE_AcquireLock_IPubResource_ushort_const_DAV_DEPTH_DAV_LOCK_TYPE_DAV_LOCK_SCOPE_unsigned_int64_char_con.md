# MEM_STORE::AcquireLock(IPubResource *,ushort const *,DAV_DEPTH,DAV_LOCK_TYPE,DAV_LOCK_SCOPE,unsigned __int64,char const *,ushort const *,IPubLock * *)

- ea: `0x180001c70`
- end: `0x180002054`
- name: `?AcquireLock@MEM_STORE@@UEAAJPEAVIPubResource@@PEBGW4DAV_DEPTH@@W4DAV_LOCK_TYPE@@W4DAV_LOCK_SCOPE@@_KPEBD1PEAPEAVIPubLock@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall ***)(_QWORD), const unsigned __int16 *, int, int, int, __int64, __int64, const unsigned __int16 *, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001c70`
- `0x180002094`
- `0x180002b2c`
- `0x180003c06`
- `0x180003c30`
- `0x180003cc0`
- `0x180004010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001ff6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001ff6`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001d9a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001d9a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002022`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002022`
- `iisutil!SAFE_snwprintf` at `0x180001e58`
- `iisutil!SAFE_snwprintf` at `0x180001e58`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001f37`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001f67`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001f85`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001f98`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001f37`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001f67`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001f85`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001f98`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001cd4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001e8c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001e96`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001ea3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001eb0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001cd4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001e8c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001e96`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001ea3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001eb0`

## string_xrefs

- `0x180001e40`: `opaquelocktoken:%s.%016I64x`

## pseudocode

```c
__int64 __fastcall MEM_STORE::AcquireLock(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD),
        const unsigned __int16 *a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        const unsigned __int16 *a9,
        _QWORD *a10)
{
  _DWORD *v11; // rbx
  int v13; // edi
  __int64 v14; // rax
  wchar_t *v15; // rax
  bool v16; // zf
  __int64 v17; // r8
  __int64 v18; // rax
  const unsigned __int16 *v19; // r14
  const unsigned __int16 *v20; // r12
  int v21; // edx
  BOOL v22; // eax
  _QWORD *v23; // r8
  _BYTE v27[32]; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v28; // [rsp+60h] [rbp-A0h]
  void **v29; // [rsp+80h] [rbp-80h] BYREF
  void **v30; // [rsp+88h] [rbp-78h] BYREF
  char v31; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v32; // [rsp+358h] [rbp+258h]
  int v33; // [rsp+360h] [rbp+260h]
  char *v34; // [rsp+368h] [rbp+268h]
  __int64 v35; // [rsp+370h] [rbp+270h]
  __int64 v36; // [rsp+378h] [rbp+278h]
  __int64 v37; // [rsp+380h] [rbp+280h]
  _BYTE v38[1048]; // [rsp+388h] [rbp+288h] BYREF
  int v39; // [rsp+7A0h] [rbp+6A0h]
  _BYTE v40[1048]; // [rsp+7A8h] [rbp+6A8h] BYREF
  int v41; // [rsp+BC0h] [rbp+AC0h]
  _BYTE v42[1048]; // [rsp+BC8h] [rbp+AC8h] BYREF
  int v43; // [rsp+FE0h] [rbp+EE0h]
  _BYTE v44[1048]; // [rsp+FE8h] [rbp+EE8h] BYREF
  int v45; // [rsp+1400h] [rbp+1300h]
  __int64 v46; // [rsp+1408h] [rbp+1308h]

  v11 = 0;
  STRU::STRU((STRU *)v27);
  v32 = 0;
  v29 = &LOCK_SET::`vftable';
  v33 = 0;
  v30 = &URI_LOCK_LIST::`vftable';
  v35 = 0;
  v34 = &v31;
  v36 = 0;
  v37 = 0;
  v39 = 0;
  memset_0(v38, 0, sizeof(v38));
  v41 = 0;
  memset_0(v40, 0, sizeof(v40));
  v43 = 0;
  memset_0(v42, 0, sizeof(v42));
  v45 = 0;
  memset_0(v44, 0, sizeof(v44));
  v46 = 0;
  *a10 = 0;
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 88));
  if ( *(_DWORD *)(a1 + 104) >= *(_DWORD *)(a1 + 100) )
  {
    v13 = -1917902928;
    goto LABEL_28;
  }
  v14 = (**a2)(a2);
  v13 = ((__int64 (__fastcall *)(void ***, __int64))v30[1])(&v30, v14);
  if ( v13 >= 0 )
  {
    v15 = (wchar_t *)(**a2)(a2);
    v13 = MEM_STORE::BuildLockSetForUri((MEM_STORE *)a1, v15, (struct IPubLockSet *)&v29, 3u);
    if ( v13 >= 0 )
    {
      if ( a6 )
      {
        v16 = (_DWORD)v46 == 0;
      }
      else
      {
        if ( (_DWORD)v46 )
        {
LABEL_9:
          v13 = -1917904272;
          goto LABEL_28;
        }
        v16 = HIDWORD(v46) == 0;
      }
      if ( !v16 )
        goto LABEL_9;
      v17 = *(_QWORD *)(a1 + 48);
      ++*(_QWORD *)(a1 + 8);
      v13 = SAFE_snwprintf((struct STRU *)v27, L"opaquelocktoken:%s.%016I64x", v17);
      if ( v13 >= 0 )
      {
        v11 = operator new(0x120u);
        if ( !v11 )
        {
          v13 = -2147024882;
LABEL_27:
          v11 = 0;
          goto LABEL_28;
        }
        *(_QWORD *)v11 = &MEM_LOCK::`vftable';
        STRU::STRU((STRU *)(v11 + 8));
        STRU::STRU((STRU *)(v11 + 22));
        STRU::STRU((STRU *)(v11 + 36));
        STRU::STRU((STRU *)(v11 + 50));
        v11[6] = 1;
        v11[64] = -1;
        *((_QWORD *)v11 + 33) = -1;
        v11[68] = -1;
        v11[69] = -1;
        *((_QWORD *)v11 + 35) = 0;
        v18 = (**a2)(a2);
        v19 = v28;
        v20 = (const unsigned __int16 *)v18;
        *((_QWORD *)v11 + 33) = a7;
        v11[69] = a5;
        v11[64] = a4;
        v11[68] = a6;
        if ( a9 )
        {
          v13 = STRU::Copy((STRU *)(v11 + 36), a9);
          if ( v13 < 0 )
          {
LABEL_22:
            if ( v13 < 0 )
              goto LABEL_28;
            v23 = *(_QWORD **)(a1 + 80);
            if ( *v23 != a1 + 72 )
              __fastfail(3u);
            *((_QWORD *)v11 + 1) = a1 + 72;
            *((_QWORD *)v11 + 2) = v23;
            *v23 = v11 + 2;
            *(_QWORD *)(a1 + 80) = v11 + 2;
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 8LL))(v11);
            *a10 = v11;
            ++*(_DWORD *)(a1 + 104);
            goto LABEL_27;
          }
          v21 = 1;
        }
        else
        {
          v13 = 0;
          v21 = 0;
        }
        v22 = (int)a3;
        v11[70] = v21;
        if ( a3 )
        {
          v13 = STRU::Copy((STRU *)(v11 + 50), a3);
          v22 = v13 >= 0;
        }
        v11[71] = v22;
        if ( v13 >= 0 )
        {
          v13 = STRU::Copy((STRU *)(v11 + 8), v19);
          if ( v13 >= 0 )
            v13 = STRU::Copy((STRU *)(v11 + 22), v20);
        }
        goto LABEL_22;
      }
    }
  }
LABEL_28:
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 88));
  if ( v11 )
    (**(void (__fastcall ***)(void *, __int64))v11)(v11, 1);
  LOCK_SET::~LOCK_SET((LOCK_SET *)&v29);
  STRU::~STRU((STRU *)v27);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180001c70  mov     [rsp-8+arg_18], rbx
0x180001c75  push    rbp
0x180001c76  push    rsi
0x180001c77  push    rdi
0x180001c78  push    r12
0x180001c7a  push    r13
0x180001c7c  push    r14
0x180001c7e  push    r15
0x180001c80  lea     rbp, [rsp-1320h]
0x180001c88  mov     eax, 1420h
0x180001c8d  call    _alloca_probe
0x180001c92  sub     rsp, rax
0x180001c95  mov     rax, cs:__security_cookie
0x180001c9c  xor     rax, rsp
0x180001c9f  mov     [rbp+1350h+var_40], rax
0x180001ca6  mov     rdi, [rbp+1350h+arg_48]
0x180001cad  mov     rsi, rcx
0x180001cb0  mov     r13, [rbp+1350h+arg_40]
0x180001cb7  lea     rcx, [rsp+1450h+var_1410]
0x180001cbc  xor     r12d, r12d
0x180001cbf  mov     [rsp+1450h+var_1420], rdi
0x180001cc4  mov     ebx, r12d
0x180001cc7  mov     [rsp+1450h+var_1430], r9d
0x180001ccc  mov     [rsp+1450h+var_1428], r8
0x180001cd1  mov     r14, rdx
0x180001cd4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001cda  lea     rax, ??_7LOCK_SET@@6B@; const LOCK_SET::`vftable'
0x180001ce1  mov     [rbp+1350h+var_10F8], r12
0x180001ce8  mov     [rbp+1350h+var_13D0], rax
0x180001cec  lea     rcx, [rbp+1350h+var_10C8]; void *
0x180001cf3  lea     rax, ??_7URI_LOCK_LIST@@6B@; const URI_LOCK_LIST::`vftable'
0x180001cfa  mov     [rbp+1350h+var_10F0], r12d
0x180001d01  mov     [rbp+1350h+var_13C8], rax
0x180001d05  mov     r15d, 418h
0x180001d0b  lea     rax, [rbp+1350h+var_1378]
0x180001d0f  mov     [rbp+1350h+var_10E0], r12
0x180001d16  mov     r8d, r15d; Size
0x180001d19  mov     [rbp+1350h+var_10E8], rax
0x180001d20  xor     edx, edx; Val
0x180001d22  mov     [rbp+1350h+var_10D8], r12
0x180001d29  mov     [rbp+1350h+var_10D0], r12
0x180001d30  mov     [rbp+1350h+var_CB0], r12d
0x180001d37  call    memset_0
0x180001d3c  mov     r8d, r15d; Size
0x180001d3f  mov     [rbp+1350h+var_890], r12d
0x180001d46  xor     edx, edx; Val
0x180001d48  lea     rcx, [rbp+1350h+var_CA8]; void *
0x180001d4f  call    memset_0
0x180001d54  mov     r8d, r15d; Size
0x180001d57  mov     [rbp+1350h+var_470], r12d
0x180001d5e  xor     edx, edx; Val
0x180001d60  lea     rcx, [rbp+1350h+var_888]; void *
0x180001d67  call    memset_0
0x180001d6c  mov     r8d, r15d; Size
0x180001d6f  mov     [rbp+1350h+var_50], r12d
0x180001d76  xor     edx, edx; Val
0x180001d78  lea     rcx, [rbp+1350h+var_468]; void *
0x180001d7f  call    memset_0
0x180001d84  lea     rax, [rsi+58h]
0x180001d88  mov     [rbp+1350h+var_48], r12
0x180001d8f  mov     rcx, rax
0x180001d92  mov     [rdi], r12
0x180001d95  mov     [rsp+1450h+var_1418], rax
0x180001d9a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180001da0  mov     eax, [rsi+64h]
0x180001da3  cmp     [rsi+68h], eax
0x180001da6  jb      short loc_180001DB2
0x180001da8  mov     edi, 8DAF1FB0h
0x180001dad  jmp     loc_180001FF1
0x180001db2  mov     rax, [r14]
0x180001db5  mov     rcx, r14
0x180001db8  mov     rax, [rax]
0x180001dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dc0  mov     rdx, rax
0x180001dc3  lea     rcx, [rbp+1350h+var_13C8]
0x180001dc7  mov     rax, [rbp+1350h+var_13C8]
0x180001dcb  mov     rax, [rax+8]
0x180001dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dd4  mov     edi, eax
0x180001dd6  test    eax, eax
0x180001dd8  js      loc_180001FF1
0x180001dde  mov     rax, [r14]
0x180001de1  mov     rcx, r14
0x180001de4  mov     rax, [rax]
0x180001de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dec  mov     rdx, rax; String1
0x180001def  lea     r8, [rbp+1350h+var_13D0]; struct IPubLockSet *
0x180001df3  mov     r9d, 3; unsigned int
0x180001df9  mov     rcx, rsi; this
0x180001dfc  call    ?BuildLockSetForUri@MEM_STORE@@AEAAJPEBGPEAVIPubLockSet@@K@Z; MEM_STORE::BuildLockSetForUri(ushort const *,IPubLockSet *,ulong)
0x180001e01  mov     edi, eax
0x180001e03  test    eax, eax
0x180001e05  js      loc_180001FF1
0x180001e0b  mov     r15d, [rbp+1350h+arg_28]
0x180001e12  test    r15d, r15d
0x180001e15  jnz     short loc_180001E33
0x180001e17  cmp     dword ptr [rbp+1350h+var_48], r12d
0x180001e1e  ja      short loc_180001E29
0x180001e20  cmp     dword ptr [rbp+1350h+var_48+4], r12d
0x180001e27  jbe     short loc_180001E3C
0x180001e29  mov     edi, 8DAF1A70h
0x180001e2e  jmp     loc_180001FF1
0x180001e33  cmp     dword ptr [rbp+1350h+var_48], r12d
0x180001e3a  jmp     short loc_180001E27
0x180001e3c  mov     r9, [rsi+8]
0x180001e40  lea     rdx, aOpaquelocktoke; "opaquelocktoken:%s.%016I64x"
0x180001e47  mov     r8, [rsi+30h]
0x180001e4b  lea     rcx, [rsp+1450h+var_1410]
0x180001e50  lea     rax, [r9+1]
0x180001e54  mov     [rsi+8], rax
0x180001e58  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180001e5e  mov     edi, eax
0x180001e60  test    eax, eax
0x180001e62  js      loc_180001FF1
0x180001e68  mov     ecx, 120h; Size
0x180001e6d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e72  mov     rbx, rax
0x180001e75  test    rax, rax
0x180001e78  jz      loc_180001FE9
0x180001e7e  lea     rax, ??_7MEM_LOCK@@6B@; const MEM_LOCK::`vftable'
0x180001e85  lea     rcx, [rbx+20h]
0x180001e89  mov     [rbx], rax
0x180001e8c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001e92  lea     rcx, [rbx+58h]
0x180001e96  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001e9c  lea     rcx, [rbx+90h]
0x180001ea3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001ea9  lea     rcx, [rbx+0C8h]
0x180001eb0  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001eb6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001eba  mov     dword ptr [rbx+18h], 1
0x180001ec1  mov     [rbx+100h], eax
0x180001ec7  mov     rcx, r14
0x180001eca  mov     [rbx+108h], rax
0x180001ed1  mov     [rbx+110h], eax
0x180001ed7  mov     [rbx+114h], eax
0x180001edd  mov     [rbx+118h], r12
0x180001ee4  mov     rax, [r14]
0x180001ee7  mov     rax, [rax]
0x180001eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eef  mov     r14, [rsp+1450h+var_13F0]
0x180001ef4  mov     r12, rax
0x180001ef7  mov     rcx, [rbp+1350h+arg_30]
0x180001efe  mov     eax, [rsp+1450h+var_1430]
0x180001f02  mov     [rbx+108h], rcx
0x180001f09  mov     ecx, [rbp+1350h+arg_20]
0x180001f0f  mov     [rbx+114h], ecx
0x180001f15  mov     [rbx+100h], eax
0x180001f1b  mov     [rbx+110h], r15d
0x180001f22  test    r13, r13
0x180001f25  jnz     short loc_180001F2D
0x180001f27  xor     edi, edi
0x180001f29  xor     edx, edx
0x180001f2b  jmp     short loc_180001F48
0x180001f2d  lea     rcx, [rbx+90h]
0x180001f34  mov     rdx, r13
0x180001f37  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001f3d  mov     edi, eax
0x180001f3f  test    eax, eax
0x180001f41  js      short loc_180001FA0
0x180001f43  mov     edx, 1
0x180001f48  mov     rax, [rsp+1450h+var_1428]
0x180001f4d  mov     ecx, 118h
0x180001f52  mov     r8, rbx
0x180001f55  mov     [rbx+rcx], edx
0x180001f58  test    rax, rax
0x180001f5b  jz      short loc_180001F74
0x180001f5d  lea     rcx, [rbx+0C8h]
0x180001f64  mov     rdx, rax
0x180001f67  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001f6d  mov     edi, eax
0x180001f6f  not     eax
0x180001f71  shr     eax, 1Fh
0x180001f74  mov     [rbx+11Ch], eax
0x180001f7a  test    edi, edi
0x180001f7c  js      short loc_180001FA0
0x180001f7e  lea     rcx, [rbx+20h]
0x180001f82  mov     rdx, r14
0x180001f85  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001f8b  mov     edi, eax
0x180001f8d  test    eax, eax
0x180001f8f  js      short loc_180001FA0
0x180001f91  lea     rcx, [rbx+58h]
0x180001f95  mov     rdx, r12
0x180001f98  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001f9e  mov     edi, eax
0x180001fa0  xor     r12d, r12d
0x180001fa3  test    edi, edi
0x180001fa5  js      short loc_180001FF1
0x180001fa7  lea     rdx, [rsi+48h]
0x180001fab  mov     r8, [rdx+8]
0x180001faf  cmp     [r8], rdx
0x180001fb2  jz      short loc_180001FBB
0x180001fb4  lea     ecx, [r12+3]
0x180001fb9  int     29h; Win8: RtlFailFast(ecx)
0x180001fbb  lea     rax, [rbx+8]
0x180001fbf  mov     rcx, rbx
0x180001fc2  mov     [rax], rdx
0x180001fc5  mov     [rax+8], r8
0x180001fc9  mov     [r8], rax
0x180001fcc  mov     [rdx+8], rax
0x180001fd0  mov     rax, [rbx]
0x180001fd3  mov     rax, [rax+8]
0x180001fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fdc  mov     rax, [rsp+1450h+var_1420]
0x180001fe1  mov     [rax], rbx
0x180001fe4  inc     dword ptr [rsi+68h]
0x180001fe7  jmp     short loc_180001FEE
0x180001fe9  mov     edi, 8007000Eh
0x180001fee  mov     rbx, r12
0x180001ff1  mov     rcx, [rsp+1450h+var_1418]
0x180001ff6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001ffc  test    rbx, rbx
0x180001fff  jz      short loc_180002014
0x180002001  mov     rax, [rbx]
0x180002004  mov     edx, 1
0x180002009  mov     rcx, rbx
0x18000200c  mov     rax, [rax]
0x18000200f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002014  lea     rcx, [rbp+1350h+var_13D0]; this
0x180002018  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000201d  lea     rcx, [rsp+1450h+var_1410]
0x180002022  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002028  mov     eax, edi
0x18000202a  mov     rcx, [rbp+1350h+var_40]
0x180002031  xor     rcx, rsp; StackCookie
0x180002034  call    __security_check_cookie
0x180002039  mov     rbx, [rsp+1450h+arg_18]
0x180002041  add     rsp, 1420h
0x180002048  pop     r15
0x18000204a  pop     r14
0x18000204c  pop     r13
0x18000204e  pop     r12
0x180002050  pop     rdi
0x180002051  pop     rsi
0x180002052  pop     rbp
0x180002053  retn
```
