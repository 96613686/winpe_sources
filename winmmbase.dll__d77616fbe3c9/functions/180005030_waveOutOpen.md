# waveOutOpen

- ea: `0x180005030`
- end: `0x1800055a6`
- name: `waveOutOpen`
- size: `1398`
- prototype: `MMRESULT __stdcall(LPHWAVEOUT phwo, UINT uDeviceID, LPCWAVEFORMATEX pwfx, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180005030`

## callees

- `0x180001564`
- `0x180004480`
- `0x180004534`
- `0x180005030`
- `0x1800065d0`
- `0x180007d70`
- `0x180007dd0`
- `0x18000aef0`
- `0x18000e0d0`
- `0x1800106c0`
- `0x18001d4d4`
- `0x18001d52c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800051b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800051b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800051cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005210`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005567`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800051cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005210`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005567`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005118`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005226`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005359`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005118`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005226`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005359`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000516a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005246`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000536c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000546b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005586`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000516a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005246`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000536c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000546b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005586`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180005487`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180005487`

## pseudocode

```c
MMRESULT __stdcall waveOutOpen(
        LPHWAVEOUT phwo,
        UINT uDeviceID,
        LPCWAVEFORMATEX pwfx,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  DWORD v8; // r15d
  __int64 v9; // rcx
  __int64 *v10; // rbx
  UINT v11; // r14d
  UINT v12; // eax
  HWAVEOUT v13; // r12
  unsigned int Value; // eax
  signed int v15; // esi
  void *v16; // rdi
  MMRESULT v17; // edi
  __int64 v19; // rax
  struct _MMDRV *v20; // rbx
  int v21; // eax
  LPHWAVEOUT v22; // rax
  UINT v23; // ebx
  MMRESULT v24; // [rsp+40h] [rbp-69h] BYREF
  UINT v25; // [rsp+44h] [rbp-65h] BYREF
  LPCWAVEFORMATEX pwfxa; // [rsp+48h] [rbp-61h]
  LPHWAVEOUT phwoa; // [rsp+50h] [rbp-59h]
  DWORD_PTR dwCallbacka; // [rsp+58h] [rbp-51h]
  __int64 v29; // [rsp+60h] [rbp-49h] BYREF
  _OWORD v30[3]; // [rsp+68h] [rbp-41h] BYREF
  struct _MMDRV *v31[2]; // [rsp+98h] [rbp-11h] BYREF

  dwCallbacka = dwCallback;
  pwfxa = pwfx;
  phwoa = phwo;
  v31[0] = 0;
  v25 = 0;
  v29 = 0;
  memset(v30, 0, 44);
  if ( pwfx )
  {
    if ( !dwCallback || (HIWORD(fdwOpen) & 7) != 1 )
    {
LABEL_3:
      if ( uDeviceID == 0xFFFF )
      {
        uDeviceID = -1;
      }
      else if ( uDeviceID != -1 )
      {
        if ( (fdwOpen & 0x7E10) == 0 )
        {
LABEL_6:
          if ( pwfx->wFormatTag == 1 || !pwfx->cbSize || pwfx != (LPCWAVEFORMATEX)-18LL )
          {
            v8 = fdwOpen & 1;
            v24 = v8;
            if ( (fdwOpen & 1) != 0 )
            {
              phwoa = 0;
              goto LABEL_9;
            }
            if ( phwo )
            {
              *phwo = 0;
              if ( (WinMMEnableBits & 1) != 0 )
                McGenEventWrite_EventWriteTransfer(phwo, WAVEOUT_OPEN_ENTER, pwfx, 1, v31);
LABEL_9:
              ClientUpdatePnpInfo();
              if ( wTotalWaveOutDevs )
              {
                if ( (fdwOpen & 4) != 0 || uDeviceID == -1 )
                {
                  WaveMapperInit();
                  EnterCriticalSection(&NumDevsCritSec);
                  v10 = (__int64 *)waveoutdrvZ;
                  v11 = 0;
                  if ( (_UNKNOWN *)waveoutdrvZ != &waveoutdrvZ )
                  {
                    while ( (v10[14] & 2) == 0 )
                    {
                      v10 = (__int64 *)*v10;
                      if ( v10 == (__int64 *)&waveoutdrvZ )
                        goto LABEL_30;
                    }
LABEL_16:
                    if ( v10 != (__int64 *)&waveoutdrvZ )
                    {
                      _InterlockedIncrement((volatile signed __int32 *)v10 + 23);
                      v31[0] = (struct _MMDRV *)v10;
                      v25 = v11;
                      LeaveCriticalSection(&NumDevsCritSec);
                      if ( uDeviceID != -1 || v10[10] )
                      {
                        if ( (fdwOpen & 1) != 0 )
                        {
                          v13 = 0;
                        }
                        else
                        {
                          v19 = NewHandle(1, v10[12], 32);
                          v13 = (HWAVEOUT)v19;
                          if ( !v19 )
                          {
                            mregDecUsagePtr((struct _MMDRV *)v10);
                            v17 = 7;
                            goto LABEL_61;
                          }
                          EnterCriticalSection((LPCRITICAL_SECTION)(v19 - 40));
                          *((_DWORD *)v13 - 17) |= 2u;
                          LeaveCriticalSection(&HandleListCritSec);
                          *(_QWORD *)v13 = v10;
                          *((_DWORD *)v13 + 2) = v11;
                          *((_DWORD *)v13 + 6) = uDeviceID;
                          *((_DWORD *)v13 + 7) = 0;
                        }
                        *(_QWORD *)&v30[1] = dwCallbacka;
                        *((_QWORD *)&v30[1] + 1) = dwInstance;
                        *((_QWORD *)&v30[0] + 1) = pwfxa;
                        *(_QWORD *)&v30[0] = v13;
                        LODWORD(v30[2]) = uDeviceID;
                        *(_QWORD *)((char *)&v30[2] + 4) = v10[13];
                        Value = (unsigned int)TlsGetValue(gTlsIndex);
                        v15 = Value;
                        if ( uDeviceID != -1 )
                        {
                          v16 = (void *)(int)(Value + 1);
                          TlsSetValue(gTlsIndex, v16);
                          if ( (v10[14] & 4) != 0 )
                            TlsSetValue(gTlsIndex, v16);
                        }
                        if ( v15 )
                          gfDisablePreferredDeviceReordering = 1;
                        v17 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *, _OWORD *, _QWORD))v10[10])(
                                v11,
                                5,
                                &v29,
                                v30,
                                fdwOpen);
                        TlsSetValue(gTlsIndex, (LPVOID)v15);
                        if ( v13 )
                        {
                          if ( v17 )
                          {
                            LeaveCriticalSection((LPCRITICAL_SECTION)v13 - 1);
                            FreeHandle(v13);
                          }
                          else
                          {
                            v22 = phwoa;
                            *((_QWORD *)v13 + 2) = v29;
                            *((_DWORD *)v13 - 17) &= ~2u;
                            *v22 = v13;
                            _InterlockedIncrement((volatile signed __int32 *)v10 + 23);
                            LeaveCriticalSection((LPCRITICAL_SECTION)v13 - 1);
                          }
                        }
                        EnterCriticalSection(&NumDevsCritSec);
                        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 23, 0xFFFFFFFF) == 1 )
                          mregRemoveDriver((struct _MMDRV *)v10);
                        LeaveCriticalSection(&NumDevsCritSec);
                      }
                      else
                      {
                        mregDecUsagePtr((struct _MMDRV *)v10);
                        if ( (fdwOpen & 4) != 0 )
                        {
                          v24 = waveReferenceDriverById(&waveoutdrvZ, 0xFFFFFFFFLL, v31, &v25);
                          v17 = v24;
                          if ( !v24 )
                          {
                            v20 = v31[0];
                            v21 = mregHandleInternalMessages(v31[0], 0, 0, (__int64)&v24);
                            v17 = v24;
                            if ( !v21 && !v24 )
                              v17 = waveOutOpen(phwoa, 0xFFFFFFFF, pwfxa, dwCallbacka, dwInstance, fdwOpen & 0xFFFFFFFB);
                            mregDecUsagePtr(v20);
                          }
                        }
                        else
                        {
                          v23 = 0;
                          v17 = 4;
                          if ( wTotalWaveOutDevs )
                          {
                            do
                            {
                              v17 = waveOutOpen(phwoa, v23, pwfxa, dwCallbacka, dwInstance, fdwOpen);
                              if ( !v17 )
                                break;
                              ++v23;
                            }
                            while ( v23 < wTotalWaveOutDevs );
                            v8 = v24;
                          }
                        }
                      }
LABEL_32:
                      if ( v8 )
                        return v17;
LABEL_61:
                      if ( (WinMMEnableBits & 1) != 0 )
                        McTemplateU0q_EventWriteTransfer(v9, WAVEOUT_OPEN_EXIT, v17);
                      return v17;
                    }
                  }
                }
                else
                {
                  EnterCriticalSection(&NumDevsCritSec);
                  v10 = (__int64 *)waveoutdrvZ;
                  if ( (_UNKNOWN *)waveoutdrvZ != &waveoutdrvZ )
                  {
                    v11 = uDeviceID;
                    do
                    {
                      if ( (v10[14] & 2) == 0 )
                      {
                        v12 = *((_DWORD *)v10 + 22);
                        if ( v12 > v11 )
                          goto LABEL_16;
                        v11 -= v12;
                      }
                      v10 = (__int64 *)*v10;
                    }
                    while ( v10 != (__int64 *)&waveoutdrvZ );
                  }
                }
LABEL_30:
                LeaveCriticalSection(&NumDevsCritSec);
              }
              v17 = 2;
              goto LABEL_32;
            }
          }
          return 11;
        }
        return 10;
      }
      if ( (fdwOpen & 0x7E04) == 0 )
        goto LABEL_6;
      return 10;
    }
    if ( IsWindow((HWND)dwCallback) )
    {
      pwfx = pwfxa;
      goto LABEL_3;
    }
  }
  return 11;
}

```

## disassembly

```asm
0x180005030  push    rbp
0x180005032  push    rbx
0x180005033  push    rsi
0x180005034  push    rdi
0x180005035  push    r13
0x180005037  push    r15
0x180005039  lea     rbp, [rsp-1Fh]
0x18000503e  sub     rsp, 0C8h
0x180005045  mov     rax, cs:__security_cookie
0x18000504c  xor     rax, rsp
0x18000504f  mov     [rbp+47h+var_48], rax
0x180005053  xor     esi, esi
0x180005055  mov     [rbp+47h+dwCallback], r9
0x180005059  mov     [rbp+47h+pwfx], r8
0x18000505d  xorps   xmm0, xmm0
0x180005060  mov     [rbp+47h+phwo], rcx
0x180005064  mov     edi, edx
0x180005066  mov     [rbp+47h+var_58], rsi
0x18000506a  mov     rbx, rcx
0x18000506d  mov     dword ptr [rbp+47h+var_B0+4], esi
0x180005070  mov     [rbp+47h+var_90], rsi
0x180005074  movups  [rbp+47h+var_78], xmm0
0x180005078  movups  [rbp+47h+var_78+0Ch], xmm0
0x18000507c  movups  [rbp+47h+var_88], xmm0
0x180005080  test    r8, r8
0x180005083  jz      loc_1800052EA
0x180005089  mov     r13d, [rbp+47h+fdwOpen]
0x18000508d  test    r9, r9
0x180005090  jnz     loc_180005476
0x180005096  movzx   eax, r13w
0x18000509a  cmp     edi, 0FFFFh
0x1800050a0  jz      loc_1800054E4
0x1800050a6  cmp     edi, 0FFFFFFFFh
0x1800050a9  jz      loc_1800052D8
0x1800050af  test    eax, 0FFFF7E10h
0x1800050b4  jnz     loc_1800052E3
0x1800050ba  cmp     word ptr [r8], 1
0x1800050bf  jnz     loc_18000549E
0x1800050c5  mov     r15d, r13d
0x1800050c8  and     r15d, 1
0x1800050cc  mov     dword ptr [rbp+47h+var_B0], r15d
0x1800050d0  jz      loc_1800052A3
0x1800050d6  mov     [rbp+47h+phwo], rsi
0x1800050da  mov     [rsp+0F0h+var_30], r12
0x1800050e2  mov     [rsp+0F0h+var_38], r14
0x1800050ea  call    ClientUpdatePnpInfo
0x1800050ef  cmp     cs:wTotalWaveOutDevs, esi
0x1800050f5  jz      loc_180005267
0x1800050fb  mov     r12d, r13d
0x1800050fe  and     r12d, 4
0x180005102  jnz     loc_1800052F1
0x180005108  cmp     edi, 0FFFFFFFFh
0x18000510b  jz      loc_1800052F1
0x180005111  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180005118  call    cs:__imp_EnterCriticalSection
0x18000511e  mov     rbx, cs:waveoutdrvZ
0x180005125  lea     rsi, waveoutdrvZ
0x18000512c  cmp     rbx, rsi
0x18000512f  jz      loc_18000525A
0x180005135  mov     r14d, edi
0x180005138  test    byte ptr [rbx+70h], 2
0x18000513c  jnz     loc_18000524E
0x180005142  mov     eax, [rbx+58h]
0x180005145  cmp     eax, r14d
0x180005148  jbe     loc_1800054EE
0x18000514e  cmp     rbx, rsi
0x180005151  jz      loc_18000525A
0x180005157  lock inc dword ptr [rbx+5Ch]
0x18000515b  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180005162  mov     [rbp+47h+var_58], rbx
0x180005166  mov     dword ptr [rbp+47h+var_B0+4], r14d
0x18000516a  call    cs:__imp_LeaveCriticalSection
0x180005170  cmp     edi, 0FFFFFFFFh
0x180005173  jz      loc_18000538E
0x180005179  test    r15d, r15d
0x18000517c  jz      loc_180005335
0x180005182  xor     r12d, r12d
0x180005185  mov     rax, [rbp+47h+dwCallback]
0x180005189  mov     ecx, cs:gTlsIndex; dwTlsIndex
0x18000518f  mov     qword ptr [rbp+47h+var_78], rax
0x180005193  mov     rax, [rbp+47h+dwInstance]
0x180005197  mov     qword ptr [rbp+47h+var_78+8], rax
0x18000519b  mov     rax, [rbp+47h+pwfx]
0x18000519f  mov     qword ptr [rbp+47h+var_88+8], rax
0x1800051a3  mov     qword ptr [rbp+47h+var_88], r12
0x1800051a7  mov     [rbp+47h+var_68], edi
0x1800051aa  mov     rax, [rbx+68h]
0x1800051ae  mov     [rbp+47h+var_64], rax
0x1800051b2  call    cs:__imp_TlsGetValue
0x1800051b8  mov     rsi, rax
0x1800051bb  cmp     edi, 0FFFFFFFFh
0x1800051be  jz      short loc_1800051DF
0x1800051c0  lea     ecx, [rax+1]
0x1800051c3  movsxd  rdi, ecx
0x1800051c6  mov     ecx, cs:gTlsIndex; dwTlsIndex
0x1800051cc  mov     rdx, rdi; lpTlsValue
0x1800051cf  call    cs:__imp_TlsSetValue
0x1800051d5  test    byte ptr [rbx+70h], 4
0x1800051d9  jnz     loc_18000555E
0x1800051df  test    esi, esi
0x1800051e1  jnz     loc_180005572
0x1800051e7  mov     rax, [rbx+50h]
0x1800051eb  lea     r9, [rbp+47h+var_88]
0x1800051ef  lea     r8, [rbp+47h+var_90]
0x1800051f3  mov     [rsp+0F0h+var_D0], r13
0x1800051f8  mov     edx, 5
0x1800051fd  mov     ecx, r14d
0x180005200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005205  mov     ecx, cs:gTlsIndex; dwTlsIndex
0x18000520b  mov     edi, eax
0x18000520d  movsxd  rdx, esi; lpTlsValue
0x180005210  call    cs:__imp_TlsSetValue
0x180005216  test    r12, r12
0x180005219  jnz     loc_180005444
0x18000521f  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180005226  call    cs:__imp_EnterCriticalSection
0x18000522c  mov     eax, 0FFFFFFFFh
0x180005231  lock xadd [rbx+5Ch], eax
0x180005236  cmp     eax, 1
0x180005239  jz      loc_180005599
0x18000523f  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180005246  call    cs:__imp_LeaveCriticalSection
0x18000524c  jmp     short loc_18000526C
0x18000524e  mov     rbx, [rbx]
0x180005251  cmp     rbx, rsi
0x180005254  jnz     loc_180005138
0x18000525a  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180005261  call    cs:__imp_LeaveCriticalSection
0x180005267  mov     edi, 2
0x18000526c  test    r15d, r15d
0x18000526f  jz      loc_1800054BB
0x180005275  mov     r14, [rsp+0F0h+var_38]
0x18000527d  mov     eax, edi
0x18000527f  mov     r12, [rsp+0F0h+var_30]
0x180005287  mov     rcx, [rbp+47h+var_48]
0x18000528b  xor     rcx, rsp; StackCookie
0x18000528e  call    __security_check_cookie
0x180005293  add     rsp, 0C8h
0x18000529a  pop     r15
0x18000529c  pop     r13
0x18000529e  pop     rdi
0x18000529f  pop     rsi
0x1800052a0  pop     rbx
0x1800052a1  pop     rbp
0x1800052a2  retn
0x1800052a3  test    rbx, rbx
0x1800052a6  jz      short loc_1800052EA
0x1800052a8  mov     [rbx], rsi
0x1800052ab  test    cs:WinMMEnableBits, 1
0x1800052b2  jz      loc_1800050DA
0x1800052b8  lea     rax, [rbp+47h+var_58]
0x1800052bc  mov     r9d, 1
0x1800052c2  lea     rdx, WAVEOUT_OPEN_ENTER
0x1800052c9  mov     [rsp+0F0h+var_D0], rax
0x1800052ce  call    McGenEventWrite_EventWriteTransfer
0x1800052d3  jmp     loc_1800050DA
0x1800052d8  test    eax, 0FFFF7E04h
0x1800052dd  jz      loc_1800050BA
0x1800052e3  mov     eax, 0Ah
0x1800052e8  jmp     short loc_180005287
0x1800052ea  mov     eax, 0Bh
0x1800052ef  jmp     short loc_180005287
0x1800052f1  call    WaveMapperInit
0x1800052f6  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800052fd  call    cs:__imp_EnterCriticalSection
0x180005303  mov     rbx, cs:waveoutdrvZ
0x18000530a  mov     r14d, esi
0x18000530d  lea     rsi, waveoutdrvZ
0x180005314  cmp     rbx, rsi
0x180005317  jz      loc_18000525A
0x18000531d  test    byte ptr [rbx+70h], 2
0x180005321  jnz     loc_18000514E
0x180005327  mov     rbx, [rbx]
0x18000532a  cmp     rbx, rsi
0x18000532d  jz      loc_18000525A
0x180005333  jmp     short loc_18000531D
0x180005335  mov     rdx, [rbx+60h]
0x180005339  mov     r8d, 20h ; ' '
0x18000533f  mov     ecx, 1
0x180005344  call    NewHandle
0x180005349  mov     r12, rax
0x18000534c  test    rax, rax
0x18000534f  jz      loc_18000554C
0x180005355  lea     rcx, [rax-28h]; lpCriticalSection
0x180005359  call    cs:__imp_EnterCriticalSection
0x18000535f  or      dword ptr [r12-44h], 2
0x180005365  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000536c  call    cs:__imp_LeaveCriticalSection
0x180005372  mov     [r12], rbx
0x180005376  mov     [r12+8], r14d
0x18000537b  mov     [r12+18h], edi
0x180005380  mov     dword ptr [r12+1Ch], 0
0x180005389  jmp     loc_180005185
0x18000538e  cmp     qword ptr [rbx+50h], 0
0x180005393  jnz     loc_180005179
0x180005399  mov     rcx, rbx; struct _MMDRV *
0x18000539c  call    mregDecUsagePtr
0x1800053a1  test    r12d, r12d
0x1800053a4  jz      loc_1800054F6
0x1800053aa  lea     r9, [rbp+47h+var_B0+4]
0x1800053ae  mov     edx, 0FFFFFFFFh
0x1800053b3  lea     r8, [rbp+47h+var_58]
0x1800053b7  mov     rcx, rsi
0x1800053ba  call    waveReferenceDriverById
0x1800053bf  mov     dword ptr [rbp+47h+var_B0], eax
0x1800053c2  mov     edi, eax
0x1800053c4  test    eax, eax
0x1800053c6  jnz     loc_18000526C
0x1800053cc  mov     rbx, [rbp+47h+var_58]
0x1800053d0  lea     rax, [rbp+47h+var_B0]
0x1800053d4  mov     r8d, dword ptr [rbp+47h+var_B0+4]
0x1800053d8  mov     r9d, 805h
0x1800053de  mov     [rsp+0F0h+var_C0], rax; __int64
0x1800053e3  mov     edx, 2
0x1800053e8  mov     qword ptr [rsp+0F0h+var_C8], 0; unsigned __int64
0x1800053f1  mov     rcx, rbx; struct _MMDRV *
0x1800053f4  mov     [rsp+0F0h+var_D0], 0; unsigned __int16 *
0x1800053fd  call    mregHandleInternalMessages
0x180005402  mov     edi, dword ptr [rbp+47h+var_B0]
0x180005405  test    eax, eax
0x180005407  jnz     short loc_180005437
0x180005409  test    edi, edi
0x18000540b  jnz     short loc_180005437
0x18000540d  mov     rax, [rbp+47h+dwInstance]
0x180005411  and     r13d, 0FFFFFFFBh
0x180005415  mov     r9, [rbp+47h+dwCallback]; dwCallback
0x180005419  mov     edx, 0FFFFFFFFh; uDeviceID
0x18000541e  mov     r8, [rbp+47h+pwfx]; pwfx
0x180005422  mov     rcx, [rbp+47h+phwo]; phwo
0x180005426  mov     [rsp+0F0h+var_C8], r13d; fdwOpen
0x18000542b  mov     [rsp+0F0h+var_D0], rax; dwInstance
0x180005430  call    waveOutOpen
0x180005435  mov     edi, eax
0x180005437  mov     rcx, rbx; struct _MMDRV *
0x18000543a  call    mregDecUsagePtr
0x18000543f  jmp     loc_18000526C
0x180005444  test    edi, edi
0x180005446  jnz     loc_180005581
0x18000544c  mov     rcx, [rbp+47h+var_90]
0x180005450  mov     rax, [rbp+47h+phwo]
0x180005454  mov     [r12+10h], rcx
0x180005459  and     dword ptr [r12-44h], 0FFFFFFFDh
0x18000545f  mov     [rax], r12
0x180005462  lock inc dword ptr [rbx+5Ch]
0x180005466  lea     rcx, [r12-28h]; lpCriticalSection
0x18000546b  call    cs:__imp_LeaveCriticalSection
0x180005471  jmp     loc_18000521F
0x180005476  mov     eax, r13d
0x180005479  shr     eax, 10h
0x18000547c  and     eax, 7
0x18000547f  cmp     eax, 1
0x180005482  jnz     short loc_1800054DC
0x180005484  mov     rcx, r9; hWnd
0x180005487  call    cs:__imp_IsWindow
0x18000548d  test    eax, eax
0x18000548f  jz      loc_1800052EA
0x180005495  mov     r8, [rbp+47h+pwfx]
0x180005499  jmp     loc_180005096
0x18000549e  cmp     [r8+10h], si
0x1800054a3  jz      loc_1800050C5
0x1800054a9  lea     rax, [r8+12h]
0x1800054ad  test    rax, rax
0x1800054b0  jz      loc_1800052EA
0x1800054b6  jmp     loc_1800050C5
0x1800054bb  test    cs:WinMMEnableBits, 1
0x1800054c2  jz      loc_180005275
0x1800054c8  mov     r8d, edi
0x1800054cb  lea     rdx, WAVEOUT_OPEN_EXIT
0x1800054d2  call    McTemplateU0q_EventWriteTransfer
0x1800054d7  jmp     loc_180005275
0x1800054dc  sub     eax, 2
0x1800054df  jmp     loc_180005096
0x1800054e4  mov     edi, 0FFFFFFFFh
0x1800054e9  jmp     loc_1800052D8
0x1800054ee  sub     r14d, eax
0x1800054f1  jmp     loc_18000524E
0x1800054f6  xor     ebx, ebx
0x1800054f8  mov     edi, 4
0x1800054fd  cmp     cs:wTotalWaveOutDevs, ebx
0x180005503  jbe     loc_18000526C
0x180005509  mov     rsi, [rbp+47h+dwInstance]
0x18000550d  mov     r14, [rbp+47h+pwfx]
0x180005511  mov     r12, [rbp+47h+dwCallback]
0x180005515  mov     r15, [rbp+47h+phwo]
0x180005519  mov     [rsp+0F0h+var_C8], r13d; fdwOpen
0x18000551e  mov     r9, r12; dwCallback
0x180005521  mov     r8, r14; pwfx
0x180005524  mov     [rsp+0F0h+var_D0], rsi; dwInstance
0x180005529  mov     edx, ebx; uDeviceID
0x18000552b  mov     rcx, r15; phwo
0x18000552e  call    waveOutOpen
0x180005533  mov     edi, eax
0x180005535  test    eax, eax
0x180005537  jz      short loc_180005543
0x180005539  inc     ebx
0x18000553b  cmp     ebx, cs:wTotalWaveOutDevs
0x180005541  jb      short loc_180005519
0x180005543  mov     r15d, dword ptr [rbp+47h+var_B0]
0x180005547  jmp     loc_18000526C
0x18000554c  mov     rcx, rbx; struct _MMDRV *
  ... truncated ...
```
