# CTpSrvClients::UpdateClient(ulong,ulong,CMcTpPacket *)

- ea: `0x1800100f8`
- end: `0x180010237`
- name: `?UpdateClient@CTpSrvClients@@QEAAKKKPEAVCMcTpPacket@@@Z`
- size: `319`
- prototype: `unsigned int __fastcall(CTpSrvClients *__hidden this, unsigned int, unsigned int, struct CMcTpPacket *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000fa3c`
- `0x180010c44`

## callees

- `0x1800100f8`
- `0x1800108e8`
- `0x1800247d4`
- `0x180026d3a`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180010216`
- `KERNEL32!LeaveCriticalSection` at `0x180010216`
- `KERNEL32!EnterCriticalSection` at `0x180010121`
- `KERNEL32!EnterCriticalSection` at `0x180010121`

## pseudocode

```c
__int64 __fastcall CTpSrvClients::UpdateClient(
        LPCRITICAL_SECTION *this,
        unsigned int a2,
        int a3,
        struct CMcTpPacket *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  __int64 v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rdi
  int v12; // ecx
  float v13; // xmm1_4
  float v14; // xmm0_4
  float v15; // xmm2_4
  float v16; // xmm3_4
  int v17; // eax
  float v18; // xmm1_4
  float v19; // xmm3_4

  v4 = *this;
  EnterCriticalSection(*this);
  v9 = CSmHashTable<CTpSrvClients::Client,CNoLock,113>::FindItem<unsigned long>(this + 17, a2);
  v10 = 0;
  v11 = v9;
  if ( v9 )
  {
    *(_QWORD *)(v9 + 1136) = CStopwatch::CurrentMs((CStopwatch *)(this + 359));
    if ( a3 )
    {
      v12 = *(_DWORD *)(v11 + 1144);
      v13 = 0.0;
      v14 = (float)a3;
      v15 = (float)a3 * 0.1;
      if ( v12 )
      {
        v13 = (float)v12;
        v16 = (float)((float)v12 * 0.89999998) + v15;
      }
      else
      {
        v16 = (float)a3;
      }
      if ( (int)v16 )
      {
        v18 = v13 * 0.89999998;
        if ( v12 )
          v19 = v18 + v15;
        else
          v19 = (float)a3;
        if ( (unsigned int)(int)v19 <= 0x1388 )
        {
          if ( v12 )
            v14 = v18 + v15;
          v17 = (int)v14;
        }
        else
        {
          v17 = 5000;
        }
      }
      else
      {
        v17 = 1;
      }
      *(_DWORD *)(v11 + 1144) = v17;
    }
    if ( a4 && *((_BYTE *)a4 + 4) == 5 )
      memmove_0((void *)(v11 + 1156), (char *)a4 + 3312, 3u);
  }
  else
  {
    v10 = 2;
  }
  LeaveCriticalSection(v4);
  return v10;
}

```

## disassembly

```asm
0x1800100f8  mov     [rsp+arg_0], rbx
0x1800100fd  mov     [rsp+arg_8], rbp
0x180010102  mov     [rsp+arg_10], rsi
0x180010107  push    rdi
0x180010108  push    r14
0x18001010a  push    r15
0x18001010c  sub     rsp, 20h
0x180010110  mov     r15, [rcx]
0x180010113  mov     r14, rcx
0x180010116  mov     rcx, r15; lpCriticalSection
0x180010119  mov     ebp, r8d
0x18001011c  mov     rsi, r9
0x18001011f  mov     ebx, edx
0x180010121  call    cs:__imp_EnterCriticalSection
0x180010127  lea     rcx, [r14+88h]
0x18001012e  mov     r8d, ebx
0x180010131  mov     edx, ebx
0x180010133  call    ??$FindItem@K@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@QEAAPEAUClient@CTpSrvClients@@KK@Z; CSmHashTable<CTpSrvClients::Client,CNoLock,113>::FindItem<ulong>(ulong,ulong)
0x180010138  xor     ebx, ebx
0x18001013a  mov     rdi, rax
0x18001013d  test    rax, rax
0x180010140  jnz     short loc_18001014A
0x180010142  lea     ebx, [rax+2]
0x180010145  jmp     loc_180010213
0x18001014a  lea     rcx, [r14+0B38h]; this
0x180010151  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x180010156  mov     [rdi+470h], rax
0x18001015d  test    ebp, ebp
0x18001015f  jz      loc_1800101EF
0x180010165  mov     ecx, [rdi+478h]
0x18001016b  xorps   xmm0, xmm0
0x18001016e  movss   xmm4, cs:__real@3f666666
0x180010176  xorps   xmm1, xmm1
0x180010179  cvtsi2ss xmm0, rbp
0x18001017e  movaps  xmm2, xmm0
0x180010181  mulss   xmm2, cs:__real@3dcccccd
0x180010189  test    ecx, ecx
0x18001018b  jnz     short loc_180010192
0x18001018d  movaps  xmm3, xmm0
0x180010190  jmp     short loc_1800101A2
0x180010192  cvtsi2ss xmm1, rcx
0x180010197  movaps  xmm3, xmm1
0x18001019a  mulss   xmm3, xmm4
0x18001019e  addss   xmm3, xmm2
0x1800101a2  cvttss2si rax, xmm3
0x1800101a7  cmp     eax, 1
0x1800101aa  jnb     short loc_1800101B3
0x1800101ac  mov     eax, 1
0x1800101b1  jmp     short loc_1800101E9
0x1800101b3  mulss   xmm1, xmm4
0x1800101b7  test    ecx, ecx
0x1800101b9  jnz     short loc_1800101C0
0x1800101bb  movaps  xmm3, xmm0
0x1800101be  jmp     short loc_1800101C7
0x1800101c0  movaps  xmm3, xmm1
0x1800101c3  addss   xmm3, xmm2
0x1800101c7  cvttss2si rax, xmm3
0x1800101cc  mov     edx, 1388h
0x1800101d1  cmp     eax, edx
0x1800101d3  jbe     short loc_1800101D9
0x1800101d5  mov     eax, edx
0x1800101d7  jmp     short loc_1800101E9
0x1800101d9  test    ecx, ecx
0x1800101db  jz      short loc_1800101E4
0x1800101dd  movaps  xmm0, xmm1
0x1800101e0  addss   xmm0, xmm2
0x1800101e4  cvttss2si rax, xmm0
0x1800101e9  mov     [rdi+478h], eax
0x1800101ef  test    rsi, rsi
0x1800101f2  jz      short loc_180010213
0x1800101f4  cmp     byte ptr [rsi+4], 5
0x1800101f8  jnz     short loc_180010213
0x1800101fa  lea     rdx, [rsi+0CF0h]; Src
0x180010201  mov     r8d, 3; Size
0x180010207  lea     rcx, [rdi+484h]; void *
0x18001020e  call    memmove_0
0x180010213  mov     rcx, r15; lpCriticalSection
0x180010216  call    cs:__imp_LeaveCriticalSection
0x18001021c  mov     rbp, [rsp+38h+arg_8]
0x180010221  mov     eax, ebx
0x180010223  mov     rbx, [rsp+38h+arg_0]
0x180010228  mov     rsi, [rsp+38h+arg_10]
0x18001022d  add     rsp, 20h
0x180010231  pop     r15
0x180010233  pop     r14
0x180010235  pop     rdi
0x180010236  retn
```
